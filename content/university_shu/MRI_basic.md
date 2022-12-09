---
title: "MRI_Basic"
date: 2022-12-08T15:09:46+08:00
draft: false
author: Bughht 
categories: [University]
tags: [MRI]
---

# Principle of Magnetic Resonance Imaging

## Mathematical Fundamentals

***TODO***

## Signal Generation

### Nuclear Magnetic Moments

Based on quantum mechanics, **nuclear magnetic dpole moment** $\overrightarrow{\mu}=\gamma\hbar\sqrt{I(I+1)}$.

where $\gamma$ is **gyromagnetic ratio**, $\hbar=\cfrac{h}{2\pi}$ is the **reduced Planck's constant**, $I=0,\cfrac{1}{2}, 1,\cfrac{3}{2}, 2\cdots$ is the **nuclear spin quantum number**.

For $^1H$, $^{13}C$, $^{19}F$ and $^{31}P$, $I=\frac{1}{2}$, such a spin system is called a **spin-$\bold{\frac{1}{2}}$ system**. A nucleus is NMR-active only if $I\ne0$

The z-component of $\overrightarrow{\mu}=\gamma m_I\hbar$

where $m_I=-I,-I+1，-I+2, \cdots, I$ called **magnetic quantum number** for nucleus with nonzero spin.

The angle $\theta$ between $\overrightarrow{\mu}$ and $\overrightarrow{B_0}$, $\cos\theta=\cfrac{\mu_z}{\mu}=\cfrac{m_I}{\sqrt{I(I+1)}}$

and $|\overrightarrow{\mu_{xy}}|=\sqrt{\mu^2-\mu_z^2}=\gamma\hbar\sqrt{I(I+1)-m_I^2}$, for a spin-$\frac{1}{2}$ systema, $I=\frac{1}{2}$ and $m_I=\pm\frac{1}{2}$,

$$\theta=\pm 54\degree 44'$$

$$|\overrightarrow{\mu}_{xy}|=\cfrac{\gamma\hbar}{\sqrt{2}}$$

According to classical mechanics, the torque $\overrightarrow{\mu}$ experiences from external magnetic field

$$\cfrac{d\overrightarrow{\mu}}{dt}=\gamma\overrightarrow{\mu}\times B_0\overrightarrow{k}$$

The solution of this equation of motion for isolated spins is called **nuclear precession**

$$
\begin{cases}
  \mu_{xy}(t)&=\mu_{xy}(0)e^{-i\gamma B_0 t}\\\\
  \mu_{z}(t)&=\mu_{z}(0)
\end{cases}
$$

The angular freque3ncy of nuclear precesson, also known as **Larmor Frequency** is $\omega_0=\gamma B_0$

### Bulk Magnetization

**Bulk magnetization** is a macroscopic magnetization vector $\overrightarrow{M}=\sum\limits_{n=1}^{N_s}\overrightarrow{\mu}_n$ is the vector sum of all the microscopic magnetic moments in the opject, where $N_s$ is the total number of spins in the object being imaged.

According to the quantum theory,

$$E=-\overrightarrow{\mu}\cdot\overrightarrow{B}_0=-{\mu_z}\cdot{B}_0=-\gamma\hbar m_I B_0$$

so for pointing-up and pointing-down spins

$$\begin{cases}
  E_\uparrow&=-\frac{1}{2}\gamma\hbar B_0&\text{lower-energy state}\\\\
  E_\downarrow&=\frac{1}{2}\gamma\hbar B_0&\text{higher-energy state}
\end{cases}$$

$$\Delta E=E_\downarrow-E_\uparrow = \gamma\hbar B_0$$

Based on Boltzmann relationship

$$\cfrac{N_\uparrow}{N_\downarrow}=\exp\bigg(\cfrac{\Delta E}{K T_s}\bigg)\approx 1+\cfrac{\gamma\hbar B_0}{K T_s}$$

where $T_s$ is the absolute temperature of the spin system, $K=1.38\times 10^{-23} J/K$ is the Boltzmann constant

so that $N_\uparrow-N_\downarrow\approx N_s\cfrac{\gamma\hbar B_0}{2KT_s}$, and $\frac{\gamma\hbar B_0}{2KT_s}$

Substitude the bulk magnetization with equation above gives

$$\overrightarrow{M}=\Bigg(\sum\limits_{n=1}^{N_\uparrow}\frac{1}{2}\gamma\hbar\-\sum\limits_{n=1}^{N_\uparrow}\frac{1}{2}\gamma\hbar\Bigg)\overrightarrow{k}=\frac{1}{2}(N_\uparrow-N_\downarrow)\gamma\hbar\overrightarrow{k}$$

and the **bulk magnetization vector** points along positive-z axis at equilibrium.

$$M_z^0=|\overrightarrow{M}|=\cfrac{\gamma^2\hbar^2B_0N_s}{4KT_s}$$

**NMR: low-sensitive technique** for a 1 Tesla system at 300K room temperature, $\cfrac{N_\uparrow-N_\downarrow}{N_s}\approx3\times10^{-6}$

**Isochromat**: a group of nuclear spins that share the same resonance frequency

+ Reasons for multiple isochromat
  + inhomogeneity in the $B_0$ field
  + chemical shift (the subject of NMR spectroscopy, related tio chemical structures)
    + $\hat{B}_0=B_0(1-\delta)$
    + $\hat{\omega}_0=\omega_0(1-\delta)$
    + shielding constant $\delta$, usually very small on the order of a few parts per million (ppm)
      + "fat" $CH_2$ from water $H_2O$: 3.35 ppm
    + **(Chemical shift) frequency bandwidth $\bold{\omega_M}$**: the maximum chemical shift $|\omega-\omega_0|\le\omega_M/2$

### RF Excitations

Bulk magnetization vector $\overrightarrow{M}$ points along the direction of $\overrightarrow{B}_0$, and the transverse component of $\overrightarrow{M}$ is zero vector at equilibrium because precessing magnetic moments have random phases.

Quantum model: electromagnetic radiation of frequency $\omega_{rf}$ carries energy (Planck's Law)

$$E_rf=\hbar\omega_{rf}$$

the radiation energy must be equal to the energy difference $\Delta E$ between the adjacent spin states, and comes up with the **resonance condition**

$$\hbar\omega_{rf}=\Delta E=\gamma\hbar B_0=\hbar\omega_0 \quad \Longrightarrow \quad\omega_{rf}=\omega_0$$

#### Typical RF field

$B_1(t)=-B_1^e(t)e^{-i(\omega_{rf}t+\phi)}$

where $B_1^e(t)$ is the pulse envelope function and $\omega_{rf}$ is the excitation carrier frequency

RF pulse generates $\overrightarrow{B}_1(t)$ field perpendicular to the $\overrightarrow{B}_0$ field

+ Main Params
  + excitation frequency: constant for most RF pulses, determined by resonance condition
  + envelope function: specifies the shape and duration of an RF pulse

#### Rotating reference frame

Rotating frame; a coordinate system whose transverse plane is rotating clockwise at an angular frequency $\omega$

e.g. the transformation applied in Lamor-rotation frame and RF-rotating frame
$$\begin{cases}
  \overrightarrow{i}^\prime\xlongequal{\Delta}&\cos (\omega t) \overrightarrow{i}-\sin (\omega t) \overrightarrow{j}\\\\
  \overrightarrow{j}^\prime\xlongequal{\Delta}&\sin (\omega t) \overrightarrow{i}+\cos (\omega t) \overrightarrow{j}\\\\
  \overrightarrow{k}^\prime\xlongequal{\Delta}&\overrightarrow{k}
\end{cases}$$

The introduction of rotating frame produce severral useful characteristics

+ Time derivatives of the unit directional vectors of the rotating frame are given by

$$\begin{cases}
  \frac{d\overrightarrow{i}^\prime}{dt}=\overrightarrow{\omega}\times\overrightarrow{i}^\prime\\\\
  \frac{d\overrightarrow{j}^\prime}{dt}=\overrightarrow{\omega}\times\overrightarrow{j}^\prime\\\\
  \frac{d\overrightarrow{k}^\prime}{dt}=\overrightarrow{\omega}\times\overrightarrow{k}^\prime
\end{cases}$$

where $\overrightarrow{\omega}$ is equal to $-\omega\overrightarrow{k}$ for the transformation in the example.

+ Transformation rules

$$\overrightarrow{M}\xlongequal{\Delta}M_x\overrightarrow{i}^\prime+M_x\overrightarrow{j}^\prime+M_x\overrightarrow{k}^\prime$$

$$\overrightarrow{M} _{rot}\xlongequal{\Delta}M _{x^\prime}\overrightarrow{i}^\prime+M _{y^\prime}\overrightarrow{j}^\prime+M _{z^\prime}\overrightarrow{k}^\prime$$

transformation rules could be written in matrix and complex notation

$$\begin{bmatrix}
  B_{1,x'}\\\\
  B_{1,y'}\\\\
\end{bmatrix} = \begin{bmatrix}
  \cos\omega t&-\sin\omega t\\\\
  \sin\omega t&\cos\omega t\\\\
\end{bmatrix}\begin{bmatrix}
  B_{1,x}\\\\
  B_{1,y}
\end{bmatrix}$$

equivalent to

$$B_{1,rot}(t)=B_1(t)e^{i\omega t}$$

+ rate of change

let

$$\cfrac{d\overrightarrow{M}}{dt}\xlongequal{\Delta}\cfrac{dM_x}{dt}\overrightarrow{i}+\cfrac{dM_y}{dt}\overrightarrow{j}+\cfrac{dM_z}{dt}\overrightarrow{k}$$

$$\cfrac{\partial\overrightarrow{M}_{rot}}{\partial t}\xlongequal{\Delta}\cfrac{dM_x'}{dt}\overrightarrow{i'}+\cfrac{dM_y'}{dt}\overrightarrow{j'}+\cfrac{dM_z'}{dt}\overrightarrow{k'}$$

then we yeld two foregoing equations

$$\cfrac{d\overleftarrow{M}}{dt}=\cfrac{\partial \overrightarrow{M}_{rot}}{\partial t}+\overrightarrow{\omega}\times\overrightarrow{M} _{rot}$$

#### Bloch Equation

$$\cfrac{d\overrightarrow{M}}{dt}=\gamma\overrightarrow{M}\times\overrightarrow{B}-\cfrac{M_x\overrightarrow{i}+M_y\overrightarrow{j}}{T_2}-\cfrac{(M_z-M_z^o)\overrightarrow{k}}{T_1}$$

here we ignore the T1 and T2 components. $\cfrac{d\overrightarrow{M}}{dt}=\gamma\overrightarrow{M}\times\overrightarrow{B}$, and come up with

$$\cfrac{\partial \overrightarrow{M}_{rot}}{\partial t}=\gamma\overrightarrow{M} _{rot}\times\overrightarrow{B} _{rot}-\overrightarrow{\omega}\times\overrightarrow{M} _{rot}=\gamma\overrightarrow{M} _{rot}\times\bigg(\overrightarrow{B} _{rot}+\cfrac{\overrightarrow{\omega}}{\gamma}\bigg)=\gamma\overrightarrow{M} _{rot}\times\overrightarrow{B} _{eff}$$

so that the general bloch equation could be expressed below

$$\cfrac{\partial\overrightarrow{M}}{\partial t}=\gamma\overrightarrow{M}\times\overrightarrow{B} _{eff}-\cfrac{M_x'\overrightarrow{i'}+M_y'\overrightarrow{j'}}{T_2}-\cfrac{(M_z'-M_z^o)\overrightarrow{k'}}{T_1}$$