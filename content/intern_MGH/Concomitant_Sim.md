---
title: "Concomitant Field Simulation"
date: 2025-12-20T15:09:46+08:00
draft: false
author: Bughht
categories: [MGH, Internship]
tags: [MRI, Concomitant, Simulation, GPU, PyTorch]
---

# MRI Concomitant Field Simulation Tool

> **GitHub Repository**: [bughht/concomitant_sim](https://github.com/bughht/concomitant_sim)

**`concomitant_sim`** is a fast, backend-agnostic Python package for simulating the phase accumulation caused by concomitant fields (Maxwell Terms) in MRI. It enables high-performance computations on both CPU and GPU by natively supporting NumPy arrays, PyTorch tensors, and CuPy arrays. The library uses an intelligent dispatching mechanism to adapt array operations to your inputs seamlessly.

---

## Theoretical Modeling

The phase accumulation $\Phi_c$ caused by concomitant fields is modeled by integrating the magnetic field variation $\Delta B_c$ over time. Following the standard framework established by Bernstein et al. (1998), for a system with primary linear gradients, the concomitant field $B_c$ is approximated by second-order spatial terms:

The phase $\Phi_c$ at a position $\mathbf{r} = (x, y, z)$ is given by the time integral:

$$
\Phi_c(\mathbf{r}, TE) = \gamma \int_0^{TE} \Delta B_c(\mathbf{r}, t)\\, dt
$$

Where $\Delta B_c$ is determined by the gradient waveforms $G_x(t), G_y(t), G_z(t)$:

$$
\Delta B_c(x, y, z, t) \approx \frac{1}{2B_0} \left[\left(G_x^2+G_y^2\right)z^2 + G_z^2\frac{x^2+y^2}{4} - G_x G_z\\, xz - G_y G_z\\, yz \right]
$$

### Spatial Decomposition

The field perturbation $\Delta B_c$ can be factorized into a sum of five spatial basis functions weighted by time-varying coefficients derived from gradient cross-terms:

$$
\Delta B_c(\mathbf{r}, t) = \sum_{k \in \\{xx, yy, zz, xz, yz\\}} c_k(\mathbf{r}) \cdot w_k(t)
$$

where the spatial polynomial coefficients $c_k(\mathbf{r})$ are:

$$
\begin{aligned}
c_{xx} &= \frac{x^2}{8B_0}, \quad &
c_{yy} &= \frac{y^2}{8B_0}, \quad &
c_{zz} &= \frac{z^2}{2B_0}, \\\\
c_{xz} &= -\frac{xz}{2B_0}, \quad &
c_{yz} &= -\frac{yz}{2B_0}
\end{aligned}
$$

and the time-dependent gradient cross-term weights $w_k(t)$ are:

$$
\begin{aligned}
w_{xx}(t) &= G_z^2(t), \quad &
w_{yy}(t) &= G_z^2(t), \quad &
w_{zz}(t) &= G_x^2(t) + G_y^2(t), \\\\
w_{xz}(t) &= G_x(t) G_z(t), \quad &
w_{yz}(t) &= G_y(t) G_z(t)
\end{aligned}
$$

The phase accumulation then becomes a simple weighted sum:

$$
\Phi_c(\mathbf{r}, TE) = \gamma \sum_k c_k(\mathbf{r}) \cdot \int_0^{TE} w_k(t)\\, dt
$$

---

## Key Features

- **Physics-Informed Simulation**: Calculates exact integration of 3D gradient waveform cross-terms combined with spatial polynomial coefficients to compute magnetic field variation ($\Delta B_c$).
- **Backend-Agnostic Engine**: Pass arrays from NumPy, CuPy, or PyTorch — the internal computations transparently map to the correct backend.
- **Hardware Acceleration (GPU)**: Natively supports CuPy and PyTorch for GPU-accelerated massive spin simulations.
- **Auto-Grad Compatible**: PyTorch tensors with `requires_grad=True` maintain the computational graph, unlocking backpropagation through the physics simulation.

---

## Installation

```bash
# Standard install (NumPy backend)
pip install .

# PyTorch backend for autograd & GPU support
pip install .[torch]

# CuPy backend for raw GPU speed
pip install .[cupy]

# Development setup with testing suites
pip install .[dev]
```

---

## Author

- **Haotian Hong** — [hhong6@mgh.harvard.edu](mailto:hhong6@mgh.harvard.edu)

## References

**Bernstein, M. A., Zhou, X. J., Polzin, J. A., King, K. F., Ganin, A., Pelc, N. J., & Glover, G. H. (1998).** Concomitant gradient terms in phase contrast MR: Analysis and correction. *Magnetic Resonance in Medicine*, 39(2), 300–308.

## License

This project is licensed under the [WTFPL](https://en.wikipedia.org/wiki/WTFPL) (Do What The F*ck You Want To Public License).
