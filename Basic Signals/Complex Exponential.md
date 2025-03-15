# Complex Exponential Signal

## Definition

The complex exponential signal is defined as:

$$x(t) = e^{st}$$

Where:
- **s** = **σ** + j**ω** is a complex frequency (where **s** is the complex frequency)
- **σ** is the real part
- j**ω** is the imaginary part
- **σ**, **ω** ∈ ℝ (real numbers)

## Mathematical Representation

Using Euler's formula, the complex exponential can be expressed as:

$$x(t) = e^{(\sigma + j\omega)t} = e^{\sigma t} \cdot e^{j\omega t} = e^{\sigma t}[\cos(\omega t) + j \cdot e^{\sigma t}\sin(\omega t)]$$

Where:
- **ω** = 2π**f** is the angular frequency

## Behavior for t > 0

The signal behavior depends on the value of parameter **σ**:

- **Exponentially increasing with time**: When **σ** > 0 (unstable)
- **Constant amplitude**: When **σ** = 0 (sustained oscillations)
- **Exponentially decreasing with time**: When **σ** < 0 (stable)

## Applications

Complex exponential signals are used for:

- Modeling second-order system behaviors
- Analyzing RLC circuits
- Modeling mass-spring-damper systems
- Studying transient responses in control systems

## Example

For a complex exponential signal with **s** = -0.2 + j3:

$$x(t) = e^{(-0.2 + j3)t} = e^{-0.2t}\cos(3t) + j \cdot e^{-0.2t}\sin(3t)$$

This represents a damped oscillation where the real and imaginary components both decay over time while oscillating.

## Visual Representation

The visual representation shows both the real and imaginary parts of the signal:
- Both parts oscillate at the same frequency
- For **σ** < 0 (stable case), the amplitude decreases over time
- The real and imaginary parts are 90° out of phase with each other
