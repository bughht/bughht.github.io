---
title: "ACDC Shim Waveform Optimization"
date: 2025-12-15T15:09:46+08:00
draft: false
author: Bughht
categories: [MGH, Internship]
tags: [Shim, MRI, Optimization, ACDC, B0]
---

# Shim Waveform Optimization: Method Notes

> **GitHub Repository**: [bughht/ACDC_Optim](https://github.com/bughht/ACDC_Optim)

We solve for shim coil currents that cancel a measured (or predicted) $B_0$ bias field,
subject to per-coil amplitude and total-current hardware limits. The codebase
(`ACDC_optimization.py`) provides **four solvers** for this problem, chosen according to
whether the currents are static or time-varying, and whether the amplifier chain's
temporal response (SIRF) needs to be modeled:

Naming scheme: `solve_shim_<scope>_<algorithm>`.

| Function | Use case | Method |
|---|---|---|
| `solve_shim_static_qp` | Single time frame | Exact QP (`quadprog`, Goldfarb–Idnani) |
| `solve_shim_waveform_qp` | Waveform, **no** SIRF coupling ($\mathbf{C}=\mathbf{I}$) | Exact QP per time point, parallelized (`joblib`) |
| `solve_shim_waveform_fista` | Waveform, **with** SIRF coupling | FISTA (NumPy, FFT-based `scipy.signal.convolve`, or legacy dense $\mathbf{C}$) |
| `solve_shim_waveform_fista_torch` | Waveform, with SIRF, large $T$ / GPU | FISTA (PyTorch, FFT-based `conv1d`, or legacy dense $\mathbf{C}$) |

When the SIRF convolution can be neglected, per-time-point QP gives the *exact* convex
optimum and is used directly (`solve_shim_waveform_qp`). FISTA is only needed once the
temporal convolution matrix $\mathbf{C}$ couples time points together, since that removes
the block-diagonal structure that makes per-frame QP tractable.

Both FISTA solvers accept the same three mutually exclusive SIRF specifications:

1. **`sirf_kernel`** (recommended) — a 1-D impulse-response kernel; convolution performed
   via `scipy.signal.convolve` (NumPy) or `torch.nn.functional.conv1d` (torch),
   both $O(T\log T)$ FFT-based.
2. **`conv_matrix`** (legacy) — a pre-built dense $T\times T$ Toeplitz matrix;
   $O(T^2)$ per multiply.
3. **Neither** — identity (no temporal filtering), $\mathbf{C}=\mathbf{I}$.

---

## 1) Static (single-time-point) problem: constrained least squares

Let $\mathbf{d}\in\mathbb{R}^{M}$ (`b0map`) be the measured field to cancel at $M$ spatial
voxels, and let $\mathbf{W}\in\mathbb{R}^{N_c\times M}$ (`acdc_fieldmap`) be the coil
sensitivity matrix: entry $(c,m)$ is the field produced at voxel $m$ by 1 A in coil $c$.
The shim-generated field at each voxel is $\mathbf{W}^T\mathbf{x}$, for currents
$\mathbf{x}\in\mathbb{R}^{N_c}$.

$$
\begin{aligned}
\min_{\mathbf{x}} \quad & \frac{1}{2}\|\mathbf{W}^T\mathbf{x}-\mathbf{d}\|_2^2 + \frac{\rho_x}{2}\|\mathbf{x}\|_2^2 \\\\
\text{s.t.} \quad & |x_c| \le I_{\max} \quad \forall c, \\\\
& \|\mathbf{x}\|_1 = \sum_{c=1}^{N_c}|x_c| \le I_{\Sigma,\max}.
\end{aligned}
$$

($\rho_x$ = `ridge_x` in code.) This is convex, but $\|\mathbf{x}\|_1$ is not a linear
inequality, so we reformulate it below for use with `quadprog`, which requires linear
constraints.

### Numerical scaling (important, and not optional in the implementation)

Coil sensitivity matrices can have a large spectral norm (e.g. $10^3$–$10^4$ Hz/A at 7 T),
which makes $\mathbf{W}\mathbf{W}^T$ entries $\sim 10^6$–$10^8$ and the QP Hessian's
condition number $\sim 10^{10}$. In practice this causes `quadprog` to report
"constraints are inconsistent" even though $\mathbf{x}=0,\ \mathbf{u}=0$ is always
feasible. Every solver therefore rescales, using $s=\sigma_{\max}(\mathbf{W})$:

$$
\mathbf{W}\to\mathbf{W}/s, \qquad \mathbf{d}\to\mathbf{d}/s,
$$

which leaves the unregularized least-squares minimizer unchanged; the ridge weights are
rescaled by $1/s^2$ to match. All diagnostics (NRMSE, predicted field) are computed back
on the original, unscaled data.

### Auxiliary variables for the L1 constraint

Introduce $\mathbf{u}\in\mathbb{R}^{N_c}$ with $u_c \ge |x_c|$, enforced by two linear
inequalities per channel:

$$
u_c - x_c \ge 0,\qquad u_c + x_c \ge 0,\qquad c=1,\dots,N_c.
$$

The L1 constraint becomes linear in $\mathbf{u}$: $\sum_c u_c \le I_{\Sigma,\max}$. A small
quadratic penalty $\frac{\rho_u}{2}\|\mathbf{u}\|_2^2$ (`ridge_u`) is added purely to keep
the QP Hessian strictly positive definite, as required by `quadprog` — it carries no
physical meaning and is unrelated to the data-fit term.

### Final QP (per time point)

$$
\begin{aligned}
\min_{\mathbf{x},\mathbf{u}} \quad & \frac{1}{2}\|\mathbf{W}^T\mathbf{x}-\mathbf{d}\|_2^2 + \frac{\rho_x}{2}\|\mathbf{x}\|_2^2 + \frac{\rho_u}{2}\|\mathbf{u}\|_2^2 \\\\
\text{s.t.} \quad & -I_{\max} \le x_c \le I_{\max} \quad \forall c, \\\\
& u_c - x_c \ge 0,\quad u_c + x_c \ge 0 \quad \forall c, \\\\
& \sum_{c=1}^{N_c} u_c \le I_{\Sigma,\max}.
\end{aligned}
$$

### `quadprog` standard form

`quadprog.solve_qp` solves $\min_{\mathbf{z}} \tfrac{1}{2}\mathbf{z}^T\mathbf{G}\mathbf{z}-\mathbf{a}^T\mathbf{z}$
s.t. $\mathbf{C}^T\mathbf{z}\ge\mathbf{b}$, with $\mathbf{z}=[\mathbf{x};\mathbf{u}]\in\mathbb{R}^{2N_c}$.
Expanding $\|\mathbf{W}^T\mathbf{x}-\mathbf{d}\|_2^2 = \mathbf{x}^T(\mathbf{W}\mathbf{W}^T)\mathbf{x}-2\mathbf{d}^T\mathbf{W}^T\mathbf{x}+\text{const}$
and matching the solver's factor-of-two convention (as implemented — `2*W@W.T`, `a = 2*W@d`, not the
$\tfrac12$-scaled form shown in some textbook derivations) gives:

$$
\mathbf{G}=
\begin{bmatrix}
2\,\mathbf{W}\mathbf{W}^T+\rho_x\mathbf{I} & \mathbf{0}\\\\
\mathbf{0} & \rho_u\mathbf{I}
\end{bmatrix},
\qquad
\mathbf{a}=
\begin{bmatrix}
2\,\mathbf{W}\mathbf{d}\\\\
\mathbf{0}
\end{bmatrix},
$$

with all quantities using the scaled $\mathbf{W},\mathbf{d}$ above. The five groups of
linear constraints — two box rows per channel, two auxiliary rows per channel, and one
global row for $\sum u_c \le I_{\Sigma,\max}$ — are stacked into $(\mathbf{C},\mathbf{b})$
with `meq = 0` (inequality only). `solve_shim_waveform_qp` reuses this exact
construction independently at every time point $t$ (only $\mathbf{a}$ changes, since
$\mathbf{d}(t_k)$ changes but $\mathbf{G}, \mathbf{C}, \mathbf{b}$ do not), parallelized
across time with `joblib`.

---

## 2) Waveform optimization with temporal (SIRF) coupling: FISTA

When the amplifier chain's System Impulse Response Function (SIRF) couples currents
across time, the per-frame QP above no longer decouples, and forming/factoring the full
$T\!\cdot\!N_c \times T\!\cdot\!N_c$ Hessian is impractical. Instead we use FISTA
(Nesterov-accelerated projected gradient descent) on the equivalent constrained
least-squares problem, projected each step onto the feasible set (box $\cap$ L1-ball).

### Objective

Let $T$ = number of time points, $N_c$ = number of coils, $M$ = number of spatial
voxels:

- $\mathbf{X}\in\mathbb{R}^{T\times N_c}$ — unknown current waveforms,
- $\mathbf{B}\in\mathbb{R}^{T\times M}$ (`b0_timecourse`) — target fieldmap over time,
- $\mathbf{W}\in\mathbb{R}^{N_c\times M}$ (`acdc_fieldmap`) — coil sensitivity, as above,
- $\mathbf{C}\in\mathbb{R}^{T\times T}$ (`conv_matrix`) — dense causal Toeplitz SIRF
  convolution (identity if not supplied).

$$
\min_{\mathbf{X}} \ \frac{1}{2}\|\mathbf{C}\mathbf{X}\mathbf{W}-\mathbf{B}\|_F^2 + \frac{\lambda}{2}\|\mathbf{X}\|_F^2,
$$

subject to, for every time point $t$: $|X_{t,c}|\le I_{\max}$ and
$\sum_c |X_{t,c}| \le I_{\Sigma,\max}$. ($\lambda$ = `ridge_x` — the same parameter name
as $\rho_x$/`ridge_x` in §1, since both play the identical role of a ridge penalty on the
current variable; the FISTA solvers just don't need a `ridge_u`, since there's no
auxiliary L1-slack variable here — the L1 constraint is enforced by exact projection
instead.) Note $\mathbf{B}$ and
$\mathbf{W}$ live directly in the spatial-voxel domain — there is no spherical-harmonic
basis anywhere in this formulation; the coil matrix has the same shape/meaning as in the
static case.

The same spectral-norm scaling from §1 is applied here: $\mathbf{W}\to\mathbf{W}/s$,
$\mathbf{B}\to\mathbf{B}/s$ with $s=\sigma_{\max}(\mathbf{W})$, so that
$\|\mathbf{W}_{\text{scaled}}\|_2 = 1$ exactly.

### Algorithm

Initialize $\mathbf{X}^{(0)}=\mathbf{0}$, $\mathbf{Y}^{(0)}=\mathbf{X}^{(0)}$, $t_0=1$.
At each iteration:

1. **Gradient** (w.r.t. the momentum variable $\mathbf{Y}$):
$$
\nabla f(\mathbf{Y}^{(k)}) = \mathbf{C}^T(\mathbf{C}\mathbf{Y}^{(k)}\mathbf{W}-\mathbf{B})\mathbf{W}^T + \lambda\mathbf{Y}^{(k)}.
$$

2. **Descent step**, size $\eta=1/L$:
$$
\tilde{\mathbf{X}}^{(k+1)} = \mathbf{Y}^{(k)} - \eta\,\nabla f(\mathbf{Y}^{(k)}).
$$
   Because $\|\mathbf{W}_{\text{scaled}}\|_2=1$ by construction, the Lipschitz constant
   simplifies to $L = \|\mathbf{C}\|_2^2 + \lambda$ (no separate $\|\mathbf{W}\|^2$ factor
   needed). $\|\mathbf{C}\|_2$ is estimated by power iteration for a dense/Toeplitz
   $\mathbf{C}$ (or taken as exactly 1 for the identity / no-SIRF case, and $\approx 1$ for
   a causal low-pass SIRF kernel with unit DC gain in the GPU path).

3. **Projection** onto box $\cap$ L1-ball, applied row-by-row (one $N_c$-vector per time
   point):
   - Clip to the box: $x_c \leftarrow \text{clip}(x_c,\,-I_{\max},\,I_{\max})$.
   - If $\sum_c|x_c| > I_{\Sigma,\max}$, apply the exact $O(N_c\log N_c)$ sorting-based
     Euclidean projection onto the L1-ball (Duchi et al., 2008).

   This two-step composition is the *exact* projection onto the box$\cap$L1-ball
   intersection here — not merely an approximation — because the L1-ball step only ever
   soft-thresholds (shrinks) magnitudes, so it cannot push any already-clipped
   coordinate back outside the box.

4. **Nesterov momentum update**:
$$
t_{k+1} = \frac{1+\sqrt{1+4t_k^2}}{2}, \qquad
\mathbf{Y}^{(k+1)} = \mathbf{X}^{(k+1)} + \frac{t_k-1}{t_{k+1}}\left(\mathbf{X}^{(k+1)}-\mathbf{X}^{(k)}\right).
$$

5. **Convergence check**: every `iter_step` iterations (default 5), compute the relative
   change in the (scaled) loss; stop when it falls below `tol` (default $10^{-12}$) or
   `max_iter` (default 3000) is reached.

### GPU variant (`solve_shim_waveform_fista_torch`)

Functionally identical to the NumPy FISTA above, but implemented in PyTorch for CUDA
acceleration.  The two solvers share an identical API (`sirf_kernel`, `conv_matrix`,
and all constraint/regularisation parameters have the same names and defaults).
The only difference is the backend used for the SIRF convolution:

- **NumPy**: `scipy.signal.convolve` (FFT-based, $O(T\log T)$ per coil).
- **Torch**: `torch.nn.functional.conv1d` (CUDA kernels or CPU FFT, $O(T\log T)$).

Both solvers also accept a legacy dense `conv_matrix` (with its spectral norm
estimated by power iteration).  If neither `sirf_kernel` nor `conv_matrix` is given,
$\mathbf{C}=\mathbf{I}$.

---

## 3) Solver selection guide

- **Single time frame** → `solve_shim_static_qp`.
- **Waveform, SIRF negligible** ($\mathbf{C}\approx\mathbf{I}$) → `solve_shim_waveform_qp`
  (exact per-frame QP, parallel over time). Good baseline / warm-start for the FISTA
  solvers below.
- **Waveform, with SIRF, moderate $T$, CPU** → `solve_shim_waveform_fista` (NumPy FISTA, dense
  Toeplitz $\mathbf{C}$).
- **Waveform, with SIRF, large $T$ or GPU available** → `solve_shim_waveform_fista_torch`
  (FISTA, FFT-based causal convolution, 10–100$\times$ speedup on CUDA).
