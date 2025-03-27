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
The fundamental theorem governing sampling states:

> A bandlimited signal with no frequency components higher than fₘₐₓ can be perfectly reconstructed if sampled at fₛ > 2fₘₐₓ

```mermaid
graph LR
    A[Analog Signal] -->|Sampling| B[Discrete Samples]
    B -->|Reconstruction| C[Recovered Signal]
