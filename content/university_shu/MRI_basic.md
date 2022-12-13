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

## Signal Generation & Detection

### Nuclear Magnetic Moments

Based on quantum mechanics, **nuclear magnetic dpole moment** $\overrightarrow{\mu}=\gamma\hbar\sqrt{I(I+1)}$.

where $\gamma$ is **gyromagnetic ratio**, $\hbar=\cfrac{h}{2\pi}$ is the **reduced Planck's constant**, $I=0,\cfrac{1}{2}, 1,\cfrac{3}{2}, 2\cdots$ is the **nuclear spin quantum number**.

For $^1H$, $^{13}C$, $^{19}F$ and $^{31}P$, $I=\frac{1}{2}$, such a spin system is called a **spin-$\bold{\frac{1}{2}}$ system**. A nucleus is NMR-active only if $I\ne0$

The z-component of $\overrightarrow{\mu}=\gamma m_I\hbar$

where $m_I=-I,-I+1，-I+2, \cdots, I$ called **magnetic quantum number** for nucleus with nonzero spin.

The angle $\theta$ between $\overrightarrow{\mu}$ and $\overrightarrow{B_0}$, $\cos\theta=\cfrac{\mu_z}{\mu}=\cfrac{m_I}{\sqrt{I(I+1)}}$

and $|\overrightarrow{\mu_{xy}}|=\sqrt{\mu^2-\mu_z^2}=\gamma\hbar\sqrt{I(I+1)-m_I^2}$, for a spin-$\frac{1}{2}$ systema, $I=\frac{1}{2}$ and $m_I=\pm\frac{1}{2}$,

$$\theta=\pm 54\degree 44^\prime$$

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

The angular frequency of nuclear precesson, also known as **Larmor Frequency** is $\omega_0=\gamma B_0$

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
  B_{1,x^\prime}\\\\
  B_{1,y^\prime}\\\\
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

$$\cfrac{\partial\overrightarrow{M}_{rot}}{\partial t}\xlongequal{\Delta}\cfrac{dM_x^\prime}{dt}\overrightarrow{i}^\prime+\cfrac{dM_y^\prime}{dt}\overrightarrow{j}^\prime+\cfrac{dM_z^\prime}{dt}\overrightarrow{k}^\prime$$

then we yeld two foregoing equations

$$\cfrac{d\overrightarrow{M}}{dt}=\cfrac{\partial \overrightarrow{M}_{rot}}{\partial t}+\overrightarrow{\omega}\times\overrightarrow{M} _{rot}$$

#### Bloch Equation

$$\cfrac{d\overrightarrow{M}}{dt}=\gamma\overrightarrow{M}\times\overrightarrow{B}-\cfrac{M_x\overrightarrow{i}+M_y\overrightarrow{j}}{T_2}-\cfrac{(M_z-M_z^o)\overrightarrow{k}}{T_1}$$

here we ignore the T1 and T2 components. $\cfrac{d\overrightarrow{M}}{dt}=\gamma\overrightarrow{M}\times\overrightarrow{B}$, and come up with

$$\cfrac{\partial \overrightarrow{M}_{rot}}{\partial t}=\gamma\overrightarrow{M} _{rot}\times\overrightarrow{B} _{rot}-\overrightarrow{\omega}\times\overrightarrow{M} _{rot}=\gamma\overrightarrow{M} _{rot}\times\bigg(\overrightarrow{B} _{rot}+\cfrac{\overrightarrow{\omega}}{\gamma}\bigg)=\gamma\overrightarrow{M} _{rot}\times\overrightarrow{B} _{eff}$$

so that the general bloch equation could be expressed below

$$\cfrac{\partial\overrightarrow{M}}{\partial t}=\gamma\overrightarrow{M}\times\overrightarrow{B} _{eff}-\cfrac{M_x^\prime\overrightarrow{i^\prime}+M_y^\prime\overrightarrow{j^\prime}}{T_2}-\cfrac{(M_z^\prime-M_z^o)\overrightarrow{k^\prime}}{T_1}$$

where

$$\overrightarrow{B}_{eff}=\overrightarrow{B} _{rot}+\cfrac{\overrightarrow{\omega}}{\gamma}$$

#### On-Resonance Excitations

The effective field that the nuclear spins see in the rotating frame is

$$\begin{aligned}
  \overrightarrow{B}_{eff}=&B_0\overrightarrow{k}^\prime+B_1^e(t)\overrightarrow{i}^\prime+\cfrac{\overrightarrow{\omega} _{rf}}{\gamma}\\\\
  =&\bigg(B_0-\cfrac{\omega _{rf}}{\gamma}\bigg)\overrightarrow{k}^\prime+B_1^e(t)\overrightarrow{i}^\prime\\\\
=&B_1^e(t)\overrightarrow{i}^\prime
\end{aligned}$$

according to bloch equation,

$$\cfrac{\partial\overrightarrow{M}_{rot}}{\partial t}=\gamma\overrightarrow{M} _{rot}\times B_1^e(t)\overrightarrow{i}^\prime$$

$$\begin{cases}
  \cfrac{dM _{x^\prime}}{dt}&=&0\\\\
  \cfrac{dM _{z^\prime}}{dt}&=&\gamma B _1^e(t)M _{z^\prime}\\\\
  \cfrac{dM _{y^\prime}}{dt}&=&-\gamma B_1^e(t)M _{y^\prime}
\end{cases}$$

Close-form solution to the partial differential equation, indicates the effect of the on-resonance excitation $\overrightarrow{B}_1$ field,

$$\begin{cases}
  M_{x^\prime}(t)=0\\\\
  M_{y^\prime}(t)=M_z^0\sin(\int_0^t\gamma B_1^e(\hat{t})d\hat{t})\\\\
  M_{z^\prime}(t)=M_z^0\cos(\int_0^t\gamma B_1^e(\hat{t})d\hat{t})\\\\
\end{cases}\qquad 0\le t\le \tau_p$$

for example giving a square wave $B_1^e=B_1\prod\bigg(\cfrac{t-\tau_p/2}{\tau_p}\bigg)$

the results comes with

$$\begin{cases}
  M_{x^\prime}(t)=0\\\\
  M_{y^\prime}(t)=M_z^0\sin(\omega_1t)\\\\
  M_{z^\prime}(t)=M_z^0\cos(\omega_1t)
\end{cases}\qquad 0\le t\le \tau_p$$

where $\omega_1=\gamma B_1$, so the bulk magnetization vector rotate around the x-axis on rotation frame which is also the orientation of $\overrightarrow{B}_1$

$$\overrightarrow{\omega}_1=-\gamma\overrightarrow{B}_1$$

The precession of $\overrightarrow{M}$ about the $B_1$ field called **forced precession**

**Flip angle**: the smaller angle between $\overrightarrow{M}$ and z-axis

$$\alpha=\int_0^{\tau_p}\omega_1(t)dt=\int_0^{\tau_p}\gamma B_1^e(t)dt$$

for rect pulse $\alpha=\omega_1\tau_p=\gamma B_1\tau_p$

$\overrightarrow{M}$ after $\alpha_\phi$ pulse could be expressed by

$$\overrightarrow{M}_{rot}(0 _+)=\bold{R} _{z^\prime}(\phi)\bold{R} _{x^\prime}(\alpha)\bold{R} _{z^\prime}(-\phi)\overrightarrow{M} _{rot}(0 _-)$$

$\overrightarrow{M}$ after $\alpha_{(\phi,\theta)}$ pulse could be expressed by

$$\overrightarrow{M}_{rot}(0 _+)=\bold{R} _{z^\prime}(\phi)\bold{R} _{y^\prime}(\hat{\theta})\bold{R} _{x^\prime}(\alpha)\bold{R} _{y^\prime}(-\hat{\theta})\bold{R} _{z^\prime}(-\phi)\overrightarrow{M} _{rot}(0 _-)$$

where $\hat{\theta}=-\frac{\pi}{2}+\theta$

#### Off-Resonance Excitations

$$\begin{aligned}
  \overrightarrow{B} _{eff}=&\bigg(B_0-\cfrac{\omega _{rf}}{\gamma}\bigg)\overrightarrow{k}^\prime+B _1^e(t)\overrightarrow{i}^\prime\\\\
  =&\cfrac{\Delta\omega _0}{\gamma}\overrightarrow{k}^\prime+B _1^e(t)\overrightarrow{i}^\prime
\end{aligned}$$

where $\Delta\omega_0=\omega_0-\omega _{rf}$

the bloch equation converts into

$$\begin{cases}
  \cfrac{dM _{x^\prime}}{dt}&=&\Delta\omega_0 M _{y^\prime}\\\\
  \cfrac{dM _{z^\prime}}{dt}&=&-\Delta\omega_0M {x^\prime}+\gamma B _1^e(t)M _{z^\prime}\\\\
  \cfrac{dM _{y^\prime}}{dt}&=&-\gamma B_1^e(t)M _{y^\prime}
\end{cases}$$

and it doesn't have a closed-form solution for an arbitrary envelope function $B_1^e(t)$

#### Frequency Selectivity

General Bloch equation doesn't has a close-form solution, so here introduce an approximation approach based on Fourier

Given the inverse fourier transformation of $B_1^e(t)$

$$\[\mathscr{F}B _1^e\](\omega)=\int _{-\infty}^\infty B _1e^{i\omega t}dt=\mathscr{F}^{-1}\[B _1^e(t)\]$$

Then we obtain the decomposition of $B_t(t)$ into a continum of clockwise rotating microvectors with amplitudes $\[\mathscr{F}B_1^e\](\omega)d\omega$

$$B_1(t)=\cfrac{1}{2}\int _{-infty}^\infty \[\mathscr{F}B _1^e\](\omega)e^{-i(\omega+\omega _{rf})t}d\omega$$

On the other hand, the bulk magnetization vectors could also be decomposed into

$$\overrightarrow{M}=\int _{-\infty}^\infty\overrightarrow{M}(\omega)d\omega$$

Ignoring the relaxation effects, $\[\mathscr{F}B_1^e\](\omega)$, or $|\[\mathscr{F}B_1^e\](\omega)|e^{i\phi(\omega)}$ becomes the excitation field acts on $\overrightarrow{M}(\omega+\omega_{rf})$, where $\phi(\omega)$ denotes the phase shift from the x'-axis

based on the linearity assumption,

$$\alpha(\omega)=\cfrac{|\[\mathscr{F}B _1^e\](\omega)|}{|\[\mathscr{F}B _1^e\](0)|}\alpha(\omega _{rf})$$

for a rectangle pulse $B_1^e(t)=B _1\prod(\frac{t-\tau_p/2}{\tau_p})$,

$$\begin{cases}
  \cfrac{\alpha(\omega)}{\alpha(0)}=sinc(\frac{1}{2}\omega\tau_p)\\\\
  \phi(\omega)=\frac{1}{2}\omega\tau_p
\end{cases}$$

it could excite nuclear spins resonating over a frequency range $|\omega-\omega_{rf}|<2\pi/\tau_p$

+ hard/nonselective pulse: short $\tau_p$, excite a wide frequency bandwidth
+ soft/selective pulse: long $tau_p$, excite a thin frequency band

### Free Precession & Relaxation

+ **free precession**: the precession of $\overrightarrow{M}$ about $B_0$ field after RF pulse excitation.
+ **longitudinal relaxation**: the recovery of the longitudinal magnetization $M_z$
+ **transverse relaxation**: the recovery of the transverse magnetization $M_{xy}$

The equation below is derived from rotating frame Bloch equation

$$\begin{cases}
  \cfrac{dM_{z^\prime}}{dt}=-\cfrac{M _{z^\prime}-M _z^0}{T_1}\\\\
  \cfrac{dM _{x^\prime y^\prime}}{dt}=-\cfrac{M _{x^\prime y^\prime}-M _z^0}{T_2}
\end{cases}$$

the solution is

$$\begin{cases}
  M _{x^\prime y^\prime}(t)=M _{x^\prime y^\prime}(0 _+)e^{-t/T_2}\\\\
  M _{z^\prime}(t)=M _{z}^0(1-e^{-t/T_1})+M _{z^\prime}(0 _+)e^{-t/T_1}\\\\
\end{cases}$$

decay of both longitudinal and transverse magnetization after RF pulse are exponential

$M_{z^\prime}$ remains 63% of equilibrium state after $T_1$, while $M_{x^\prime y^\prime}$ remains 37% after $T_2$

$$\begin{cases}
  M _{z^\prime}(T_1)=0.63 M _{z}^0\\\\
  M _{x^\prime y^\prime}(T_2)=0.37 M _{x^\prime y^\prime}(0 _+)
\end{cases}$$

The signal collected from receiver coil $V(t)$

$$V(t)=-\cfrac{\partial\Phi(t)}{\partial t}=-\cfrac{\partial}{\partial t}\int _{object}\overrightarrow{B} _r(r)\cdot\overrightarrow{M}(r,t)dr$$

where $\overrightarrow{B}_r$ is the laboratory frame magnetic field at location $r$

considering $M_z(r,t)$ is slowly vcarying compare to $M_x$ and $M_y$

$$V(t)=-\int_{object}\bigg[B _{r,x}(r)\cfrac{\partial M_x(r,t)}{\partial t+B _{r,y}(r)\cfrac{\partial M_y(r,t)}{\partial t}}\bigg]dr$$

the function could be rewrite into

$$V(t)=-\int_{object}\omega(r)|B _{r,xy}(r)||M _{xy}(r,0)|e^{-t/T_2}\sin [-\omega(r)t+\phi_e(r)-\phi_r(r)]dr$$

The amplitude of the signal could be obtained with **Phase sensitive detection (PSD) / signal demodulation** 

The **quadrature detection** collected is

$$S(t)=\omega_0e^{i\pi/2}\int _{object}B _{r,xy}^* (r)M _{xy}(r,0)e^{-i\gamma\int _0^t\Delta B(r\tau)d\tau}$$

or simplify into

$$S(t)=\int_{object} M _{xy}(r,0)e^{-i\Delta\omega(r)t}dt$$

## Signal Characteristics

Signal collected could be written as

$$S(t)=\int_{object} M _{xy}(r,0 _+)e^{-t/T _2(r)}e^{-i\omega(r)t}$$

where $\Delta\omega$ is replaced by $\omega$

Giving a **sspin spectral density** function $\rho(\omega)=\cfrac{dM(\omega)}{\omega}$

The equation could be rewritten into

$$S(t)=\int_{-\infty}^\infty \rho(\omega)e^{-t/T _2(\omega)}e^{-i\omega t}d\omega$$

omitting $T_2$ relaxation and replace $\rho$ with $\hat{\rho}=\frac{\rho}{2\pi}$, then we introduce

$$S(t)=\cfrac{1}{2\pi}\int _{-\infty}^\infty \hat{\rho}(\omega)e^{-i\omega t}d\omega$$

And for a spin system with $N$ isochromats at frequencies $\omega_n$

$$\rho(\omega)=\sum _{n=1}^N M _{z,n}^0\delta(\omega-\omega_n)$$

where $M_{z,n}^0$ is the equilibrium bulk magnetization of the $n$th isochromat.

for a Cauchy-Lorentzian distribution inhomogeneous field

$$\rho(\omega)=M_z^0\cfrac{(\gamma\Delta B_0)^2}{(\gamma\Delta B_0)^2+(\omega-\omega_0)^2}$$

### FID: Free Induction Decays

$$S(t)=\sin \alpha\int_{-\infty}^\infty \rho(\omega)e^{-t/T _2(\omega)}e^{-i\omega t}$$

where $\alpha$ is the flip angle for $\alpha$ pulse and $\rho(\omega)$ is the spin spectral density determining the characteristics of an FID signal.

Two basic parmeters of FID signal:

+ **amplitude**: the amplitude of the FID signal $A_f=\sin\alpha\int _{-infty}^\infty \rho(\omega)d\omega=M_z^0\sin\alpha$ for a spin system with a single spectral component resonating.
+ **decay rate**: closely related to the underlying spectral distribution

For the field of Lorentzian distribution, FID becomes

$$\begin{aligned}
  S(t) =&\sin\alpha\int _{-\infty}^\infty M _z^0\cfrac{(\gamma\Delta B _0)^2}{(\gamma\Delta B _0)^2+(\omega-\omega _0)^2}e^{-t/T _2}e^{-i\omega t}d\omega\\\\
  = &\pi M _z^0\gamma\Delta B _0\sin\alpha e^{-\gamma\Delta B _0 t}e^{-t/T _2}e^{-i\omega _0 t}\\\\
  = &\pi M _z^0\gamma\Delta B _0\sin\alpha e^{-t/T _2^\*} e^{-i\omega _0 t}\\\\
\end{aligned}$$

where $\cfrac{1}{T_2^*}=\cfrac{1}{T_2}+\gamma\Delta B_0$

Even though the definition of $T_2^\*$ is widely used, it's valid only restrictively for Cauchy-Lorentzian distribution spectral density functions. For other types of spectral density functions, envelope function of FID signal won't be exponential function, $T_2^\*$ should be an approximation of exponential.

For FID signals with more than one spectral component, the absorbation-mode spectrum is the summation of Lorentzian lines.

### RF Echoes

Distinguish **echo** from *FID*: *two-sideness*

+ side 1: from refocusing phase of a transverse magnetization
+ side 2: from the dephasing period

+ **RF Echoes**
+ **Gradient Echoes**

#### two-pulse echo

excitation scheme:

$$\alpha_1-\tau-\alpha_2$$

generate **spin echo (SE)**

for 