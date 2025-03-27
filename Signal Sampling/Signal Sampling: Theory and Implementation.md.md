# Signal Sampling: Theory and Implementation

## Table of Contents
1. [Introduction](#introduction)
2. [Nyquist-Shannon Theorem](#nyquist-shannon-theorem)
3. [Sample-and-Hold Circuit](#sample-and-hold-circuit)
4. [Practical Considerations](#practical-considerations)
5. [Python Implementation](#python-implementation)
6. [Further Reading](#further-reading)

## Introduction
Signal sampling is the process of converting a continuous-time signal into a discrete-time signal. This is fundamental in digital signal processing (DSP) and analog-to-digital conversion (ADC).

Key concepts:
- **Sampling rate (fₛ)**: Number of samples per second (Hz)
- **Sampling period (Tₛ)**: Time between samples (Tₛ = 1/fₛ)

## Nyquist-Shannon Theorem
**Core principle**:  
A signal with maximum frequency `f_max` must be sampled at:  
$\`f_s > 2 × f_max`\$  
to avoid **aliasing** (signal distortion).

**Key implications**:
- `f_Nyquist = 2 × f_max` (minimum sampling rate)
- Undersampling (`f_s < 2f_max`) causes frequency folding
