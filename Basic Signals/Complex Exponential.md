# Complex Exponential Signal

## Definition

The complex exponential signal is defined as:

**$$x(t) =** e^{st}$$

Where:
- **$s** = \sigma + j\omega$ is a complex frequency (where **$s$** is the complex frequency)
- **$\sigma$** is the real part
- **$j\omega$** is the imaginary part 
- **$\sigma**, **\omega** \in \mathbb{R}$ (real numbers)

## Mathematical Representation

Using Euler's formula, the complex exponential can be expressed as:

$$x(t) = e^{(\sigma + j\omega)t} = e^{\sigma t} \cdot e^{j\omega t} = e^{\sigma t}\cos(\omega t) + j \cdot e^{\sigma t}\sin(\omega t)$$

Where:
- **$\omega** = 2\pi f$ is the angular frequency

## Behavior for t > 0

The signal behavior depends on the value of parameter $\sigma$:

- **Exponentially increasing with time**: When $\sigma > 0$ (unstable)
- **Constant amplitude**: When $\sigma = 0$ (sustained oscillations)
- **Exponentially decreasing with time**: When $\sigma < 0$ (stable)

## Applications

Complex exponential signals are used for:

- Modeling second-order system behaviors
- Analyzing RLC circuits
- Modeling mass-spring-damper systems
- Studying transient responses in control systems

## Example

For a complex exponential signal with $s = -0.2 + j3$:

$$x(t) = e^{(-0.2 + j3)t} = e^{-0.2t}\cos(3t) + j \cdot e^{-0.2t}\sin(3t)$$

This represents a damped oscillation where the real and imaginary components both decay over time while oscillating.

## Visual Representation

The visual representation shows both the real and imaginary parts of the signal:
- Both parts oscillate at the same frequency
- For $\sigma < 0$ (stable case), the amplitude decreases over time
- The real and imaginary parts are 90° out of phase with each other
