---
title: "医学信号处理"
date: 2021-12-06T15:09:46+08:00
draft: false
author: Bughht 
categories: [University]
tags: [BME]
---

# Biomedical Signal Processing

## Typical Biomedical Signal

### EEG

+ Dr. Has Berger firstly recorded EEG signal in 1926
+ Clinical EEG

| Type   | Spectrum Range | Phenomenon                             |
| ------ | -------------- | -------------------------------------- |
| Beta   | 13-30Hz        | Frontal and parentally                 |
| Aplha  | 8-13Hz         | Occipitally                            |
| Theta  | 4-8Hz          | Children,              sleeping Adults |
| Delta  | 0.5-4Hz        | Infants, sleeping Adults               |
| Spikes | 3Hz            | Epilepsy-petit mal                     |

+ EEG signal is generated by Electro Neurophysiologic Signal
  + Spike
  + LFP: Local Field Potential
    + sEEG: stero-electroencephalography
  + ECog/iEEG
  + EEG (Non Invasive)
  + ERP

+ Scalp EEG
  + history
    + 1926, Hans Berger-EEG
    + 1933, Adrain verified EEG in Cambridge
    + 1958, Dawson designed EP University of London
    + 1967, Sutton-P300-ERP

  + Classification
    + Spontaneous EEG
    + Evoked Potentials: External Stimulations
    + Event-Related Potentials

  + EEG Lead System: International 10-20 System
    + Bipolar
    + Unipolar
  
+ EEG
  + EEG Sensor
  + Amplifier
  + Filter
  + A/D
  + Artifacts Rejection
  + EEG
  + ERP (from ERP)
  + Grand Average
  + Data analysis

+ Evoked Potentials
  + VEP(Visual EP)
    + F-VEP
    + P-VEP

+ ERPs: Event-related potential
  + Potential change when voking and revoking stimulations

+ Basic Principle of ERPs Extraction
  + EEG covers ERPs
  + Data Averaging
  + ERP characteristic
    + Constant waveform
    + Constant incubation period
  + The EEG obtained on several trials can be averaged together time-locked to the stimulus to form an event-related potential(ERP)

+ ECG
  + Collecting/Recording
    + History:
      + Augustus D. Waller (1856-1922) recorded the first human "electric potential of the heartbeat" using a capillary electrometer (1887)
      + Willem Eintowen (1860-1927) developed and Improved the string galvanometer(1901); established the theory and application to heart disease; Named PQRST(U) waves; Invented ECG leads
  + Theory of the Electrocardiogram (ECG)
    + The electrical properties of our heat can be measured non-invasively
    + ECG Principle:
      + P wave: Depolarization of the Atria
      + QRS complex: Depolarization of the ventricles
      + T wave: Repolarization of the ventricles
  
+ EMG
  + The electral source is the muscle membrane potential of about 90 mV.
  + Surface EMG

+ Others
  + Ultrasonic
  + Heart Rate

+ Signal
  + Message, Information, Signal
  + Classification
    + Continuous and discrete
      + Continuous time signal
      + Discrete time signal (Series)
    + Analog and digital
      + Analog: continuous on time and amplitude
      + Digital: discrete on time and amplitude
    + Determinate and random
      + Determinate Signal: $x(t)$ could be expressed in a time function
        + Periodic signal: $x(t)=x(nT+t)$
        + Aperiodic
      + Random Signal: a stochastic signal with whole uncertainty
        + Stationary Stochastic Signal
        + Non Stationary Stochastic Signal
    + Finite energy signal and finite power signal
    + fractal, chaotic signal

    + Classification of signals
      + Signal
        + Deterministic
          + Periodic
            + Sino-soicial
            + Complex
          + Nonperiodic
            + Almost Periodic
            + Transient
        + Stochastic
          + Stationary
            + Ergodic
            + Non-Ergodic
          + Nonstationary
            + Special type

+ Characteristics of Biomedical Signal
  + Weak signal (mv/uV)
    + Biomedical signal measurement is weak signal measurement
    + Measuring Requirements: high sensitivity, high resolution, noise superession, anti-interference
  + Strong Interference
  + Low frequency, thin bandwidth
  + Complicated, random, non stationary

+ Characteristics of Biomedical System
  + Organism
  + Openness
  + Time-Varient
  + Complexity
  + Non linearity
  + Varability

  In a nutshell, Biomedical System is an extremely complicated system

+ Basic mission of Biomedical Signal Processing
  + Motivation
    + Filter useless signal because they contaminate signal of interest
    + Extract signal in a more obvious or useful method
    + Prediction

  + Cited from Mark van Gils, Fall 2011
    + Some objectives of applications that use biosignal processing
      + Information gathering
      + Diagnosis
      + Monitoring
      + Therapy and control
      + Evaluation
    + Example: Notch Filter
    + Problems in biosignal processing
      + Accessibility
      + Variance
      + Inter-relationships and interactions among physiological system
      + Acquisition interference
      + Lack of Gold Standards

+ Fourier Transformation
  + One of the most common analysis techiniques that is used for biological signals isaimed at breaking down the signal into its different spectral (frequency) components

  + Signal Processing Alogrithm == Transformation Operator
  + Orthogonal function
    + inner products equals to 0
    + Orthogonal function set
      + continuous function meet
    $$\int_a^b\Phi_n(t)\Phi_m(t)dt=\begin{cases}
    C,&m=n\\
    0,&m\ne n\\
    \end{cases}$$
    on interval [a,b]
  + Inner Product
    + $<f(x),g(x)>=\int_a^bf(x)g(x)dx$
  + Fourier Transformation
    | Transform | Time                  | Spectrum              |
    | --------- | --------------------- | --------------------- |
    | CTFT      | Continuous, Aperiodic | Continuous, Aperiodic |
    | FS        | Continuous, Periodic  | Discrete, Aperiodic   |
    | DTFT      | Discrete, Aperiodic   | Continuous, Periodic  |
    | DFT       | Discrete, Periodic    | Discrete, Periodic    |
    + Fourier Transformation
      + $$\int_{-\infty}^\infty S(t)\cdot e^{-2\pi j \omega t}dt$$
  + Properties of DFT
    + Linearity
        $$DFT[ax(n)+by(n)]=aX(k)+bY(k)$$
    + Periodical
        $$x(n)=X(n+N), X(k)=X(k+N)$$
    + Time Reversal
        $$DFT[x(N-n)]=X(N-k)$$
    + Circular Time Shift
        $$DFT[x((n-l))_N]=X(k)e^{-j\frac{2\pi kl}{N}}$$
    + Circular Frequency Shift
        $$DFT[x(n)e^{-j\frac{2\pi nl}{N}}]=X((k-l))_N$$
    + Complex Conjugate
        $$DFT[x^{\*}(n)]=X^*(N-k)$$
    + Circular Convolution
        $$DFT[x_1(n)\otimes x_2(n)]=X_1(k)X_2(k)$$
    + Multiplication
        $$DFT[x_1(n)x_2(n)]=X_1(k)\otimes X_2(k)$$
    + Parseval's Theorem
        $$\sum_{n=0}^{N-1}x(n)x^\*(n)=\cfrac{1}{2\pi}\sum_{n=0}^{N-1}X(k)X^\*(k)$$
+ Spectrum Analysis
  + Magnitude Spectrum: $|X(\omega)|$
  + Phase Spectrum: $\theta$

+ Random/Stochastic Process
  + A Stochastic function of time $X(t,\xi)$.
+ Types of Stochastic Process
  + based on time
    + Discrete
    + Continuous
  + based on sample function
    + Deterministic stochastic process
    + Uncertain stochastic process
  + based on distribution function / density function
    + stable, normal, rayleigh, markov, ...
+ Random Signal
  + Random signal could only be described within limited accuracy and confidence.
+ Statistics of Random signal
  + Statistical average
  + Distribution
  + Statistical Features
+ Probability Distribution Function
  + 1-D probability distribution: $F_X(x_1;t_1)=P\{X(t_1)\le x_1\}$
    + probability density function: $f_x(x_1;t_1)=\cfrac{\partial F_X(x_1;t_1)}{\partial x_1}$
  + 2-D probability distribution: $F_X(x_1,x_2;t_1,t_2)=P\{X(t_1)\le x_1,X(t_2)\le x_2\}$
    + $f_x(x_1,x_2;t_1,t_2)=\cfrac{\partial^2F_X(x_1,x_2;t_1,t_2)}{\partial x_1\partial x_2}$
+ Statistical Features
  + Expectation(Mean; first moment around zero): $m_x(t)=E[X(t)]=\int_{-\infty}^\infty xf_X(x;t)dx$: DC component
  + Mean Square Value(second moment around zero): $\Psi_X(t)=E[X^2(t)]=\int_{-\infty}^\infty x^2f_X(x;t)dx$: Power
  + Variance(second moment around central): $\sigma^2_X(t)=D[X(t)]=E[X^2]=E[(X(t)-m_x(t))^2]$: Ac Power
  + $$\Psi_X(t)=m_X^2(t)+\sigma_X^2(t)$$
  + Correlation Function: $R_X(t_1,t_2)=E[X(t_1)X(t_2)]=\int_{-\infty}^\infty\int_{-\infty}^\infty x_1 x_2 f_X(x_1,x_2;t_1,t_2)dx_1dx_2$
    + When $t_1=t_2$, $\tau=0$, auto-correlation function $R_X(0)=E(X^2)$
  + Covariance function: $C_X(t_1,t_2)=E[(X(t_1)-m_X(t_1))(X(t_2)-m_X(t_2))]$
    + When $\tau=0$, $C_X(0)=\sigma^2(x)$
+ Stationary random signal
  + First order stable process(m=1): mean of the signal not relate to t
  + Second order stable process(m=2; wide sense stationary): mean and mean square value not related to t
+ Ergodic
  + relating to or denoting systems or processes with the property that, given sufficient time, they include or impinge on all points in a given space and can be represented statistically by a reasonably large selection of points.
  
+ Some typical random process
  + Gaussian/Normal process
    + $f(x)=\cfrac{1}{\sqrt{2\pi}\sigma}\exp^{-\cfrac{(x-a)^2}{2\sigma^2}}$
  + Ideal White Noise
    + $P_\xi(\omega)=\cfrac{n_0}{2} (W/Hz)$
    + $R(\tau)=\cfrac{n_0}{2}\delta(\tau)$
  + Band-limit White Noise
    + $P_\xi=\begin{cases}
        \cfrac{n_0}{2},&|f|<f_0\\
        0, &\text{otherwise}
    \end{cases}$
    + $R(\tau)=2f_0\cfrac{n_0}{2}\cfrac{\sin(w_0\tau)}{w_0\tau}$

+ Correlation
  + Similarity
  + Correlation coefficient: Pearson correlation coeffient
    + $r(X,y)=\cfrac{Cov(X,Y)}{\sqrt{Var(X)Var(Y)}}$
+ Linearity
  + $f(ax+by)=af(x)+bf(y)$
+ Nonlinear models
  + linear models are linear in the parameters which have to be estimated
+ Linear Correlation
  + Synchronism/Similarity/In-phase/Linear Relationship
  + $r_{xy}(m)=\sum_{n=-\infty}^\infty x(n)y(n+m)$
  + $r_{xy}(m)=x(n)\cdot y(n)$
  + $r_{xy}(m)=r_{yx}(-m)$
