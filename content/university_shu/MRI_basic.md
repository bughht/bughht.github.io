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
  \mu_{xy}(t)=\mu_{xy}(0)e^{-i\gamma B_0 t}\\\\
  \mu_{z}(t)=\mu_{z}(0)
\end{cases}
$$
