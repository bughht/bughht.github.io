---
title: "ACDC Dynamic B0 Field Control — Gordon Conference Showcase"
date: 2026-07-09T15:09:46+08:00
draft: false
author: Bughht
categories: [MGH, Conference]
tags: [ACDC, B0, Shim, EPI, Eddy-Current, Concomitant, Gordon]
---

# ACDC Dynamic B0 Field Control: Applications & Showcase

> **Scan the QR code below** to visit this page and access resources, code, and references.

<!-- TODO: Insert QR code image here -->
<!-- ![QR Code](/img/qr_gordon_acdc.png) -->

**Related Repositories:**
- [bughht/ACDC_Optim](https://github.com/bughht/ACDC_Optim) — Shim waveform optimization solvers
- [bughht/concomitant_sim](https://github.com/bughht/concomitant_sim) — Concomitant field simulation toolkit

---

## 1. Short-Term Eddy Current Compensation: Correcting EPI Edge Ghosts

### The Problem

In single-shot EPI, rapidly switching gradient waveforms induce **short-term eddy currents**
(decay $\tau \sim 1$–$10$ ms) in the cryostat and surrounding conductors. These eddy
currents create a time-varying $B_0$ offset during the EPI readout train that
manifests as **Nyquist (edge) ghosts** — shifted half-FOV replicas of the image
superimposed on the primary image.

Traditional pre-emphasis approaches compensate eddy currents by modifying the
gradient input waveform, but:
- Pre-emphasis is limited to linear ($x, y, z$) spatial corrections
- Eddy currents with short time constants are difficult to calibrate accurately
- Cross-term eddy currents ($G_x \to B_0$, $G_y \to B_0$) are often unaddressed

### The ACDC Solution

The **AC/DC shim array** provides 31 independent $B_0$ control channels that can
be modulated at the waveform level ($\sim$ kHz update rate). By solving the
constrained optimization (see [ACDC Optim notes](/intern_mgh/acdc_optim/)):

$\min_{\mathbf{X}} \ \frac{1}{2}\|\mathbf{C}\mathbf{X}\mathbf{W} - \mathbf{B}\|_F^2 \quad \text{s.t.} \ |X_{t,c}| \le I_{\max},\ \sum_c |X_{t,c}| \le I_{\Sigma,\max}$

we obtain shim current waveforms $\mathbf{X}(t)$ that prospectively cancel the
eddy-current-induced $B_0$ offset **at every time point** during the EPI readout.

## Preliminary Results

![ACDC Waveform](/img/MGH/image_ACDC_waveform.png)

**Fig 1.** ACDC shim current waveforms are optimized to cancel the eddy-current-induced gradient offsets during the EPI readout.

![EPI Gradient Waveform](/img/MGH/image_gradcompare.png)

**Fig 2.** EPI frequency encoding gradient waveforms $G_x(t)$ were measured with and without ACDC compensation. ACDC dynamically cancels the eddy-current-induced exponential curve in the gradient waveform, restoring the intended trapezoidal shape.

![EPI Edge Ghost Suppression](/img/MGH/image_edgeghost.png)

**Fig 3.** EPI images acquired with and without ACDC compensation. Third-order shim were unplugged in this experiment to prevent the influence of Fuzzy Ripple artifacts. The high-frequency edge ghosts (marked out by red arrow) are successfully suppressed and the image quality is restored with ACDC compensation.

---

## 2. Concomitant Field Correction: Diffusion bSSFP Artifacts

### The Problem

Diffusion bSSFP (balanced steady-state free precession) sequences
combine diffusion weighting with the high SNR efficiency of bSSFP. However:

- The bSSFP steady state is exquisitely sensitive to **off-resonance**
  ($\Delta f$), producing characteristic **banding artifacts**
- Diffusion gradients introduce **concomitant fields** that shift the local resonance frequency, resulting in second-order spatially varying $\Delta f$ across the imaging volume. Unlike the linear terms, concomitant fields cannot be refocused by the bipolar gradient waveform, introducing a **cumulative second-order phase bias** that varies with diffusion direction.

![Diffusion bSSFP Pulse Sequence](/img/MGH/image_diffbSSFP_pulseq.png)

**Fig 4.** Pulse sequence diagram of diffusion bSSFP.

### The ACDC Solution

The ACDC array can provide **dynamic, diffusion-direction-dependent**
concomitant field compensation:

1. For each diffusion direction, pre-compute the concomitant field
   $\Delta B_c(\mathbf{r}, t)$ from the diffusion gradient waveforms
2. Optimize a per-direction shim current waveform that cancels
   $\Delta B_c$ during the diffusion preparation
3. During the bSSFP readout, optionally switch to a **static shim** optimized
   for the average $B_0$ offset in the imaging volume

## Preliminary Results

![Diffusion bSSFP Concomitant Field Compensation](/img/MGH/image_ACDC_concomitant.png)

**Fig 5.** Diffusion bSSFP images acquired with and without ACDC concomitant field compensation. Circular banding artifacts caused by the z-direction concomitant field ($x^2 + y^2$ term) are successfully suppressed by prospective AC/DC concomitant fieldcompensation.
