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

$$x(t) = e^{(\sigma + j\omega)t} = e^{\sigma t} \cdot e^{j\omega t} = e^{\sigma t}\cos(\omega t) + j \cdot e^{\sigma t}\sin(\omega t)$$

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

## Code Example
```python
import sympy as sp
import numpy as np
import matplotlib.pyplot as plt
from sympy.abc import t
from sympy import I, exp, cos, sin, re, im, symbols, lambdify

# Define symbolic variables
sigma, omega = symbols('sigma omega', real=True)

# Define the complex exponential symbolically
s = sigma + I*omega
complex_exp = exp(s*t)

# Expand using Euler's formula
expanded_form = complex_exp.rewrite(cos)

# Print the symbolic forms
print("Complex exponential s*t where s = sigma + j*omega:")
print(f"x(t) = {complex_exp}")
print("\nExpanded form:")
print(f"x(t) = {expanded_form}")

# Calculate real and imaginary parts symbolically
real_part = re(complex_exp)
imag_part = im(complex_exp)

print("\nReal part:")
print(f"Re[x(t)] = {real_part}")
print("\nImaginary part:")
print(f"Im[x(t)] = {imag_part}")

# Now let's plot a specific example with sigma = -0.2 and omega = 3
sigma_val = -0.2
omega_val = 3.0

# Convert symbolic expressions to numerical functions for plotting
real_func = lambdify(t, real_part.subs({sigma: sigma_val, omega: omega_val}), 'numpy')
imag_func = lambdify(t, imag_part.subs({sigma: sigma_val, omega: omega_val}), 'numpy')
abs_func = lambdify(t, abs(complex_exp).subs({sigma: sigma_val, omega: omega_val}), 'numpy')

# Time vector for plotting
t_vals = np.linspace(0, 6, 1000)

# Create plots
plt.figure(figsize=(12, 8))

# Plot real part
plt.subplot(2, 1, 1)
plt.plot(t_vals, real_func(t_vals), 'b-')
plt.grid(True)
plt.title(f'Real Part: $e^{{{sigma_val}t}}\\cos({omega_val}t)$')
plt.ylabel('Re{$e^{st}$}')
plt.ylim(-1, 1)

# Plot imaginary part
plt.subplot(2, 1, 2)
plt.plot(t_vals, imag_func(t_vals), 'r-')
plt.grid(True)
plt.title(f'Imaginary Part: $e^{{{sigma_val}t}}\\sin({omega_val}t)$')
plt.xlabel('Time (t)')
plt.ylabel('Im{$e^{st}$}')
plt.ylim(-1, 1)

plt.tight_layout()
plt.savefig('complex_exponential_sympy.png', dpi=300)
plt.show()

# Plot the magnitude (envelope)
plt.figure(figsize=(10, 5))
plt.plot(t_vals, abs_func(t_vals), 'g-')
plt.grid(True)
plt.title(f'Magnitude: $e^{{{sigma_val}t}}$')
plt.xlabel('Time (t)')
plt.ylabel('|$e^{st}$|')
plt.savefig('complex_exponential_magnitude.png', dpi=300)
plt.show()

# Analytic analysis of stability
print("\nStability analysis:")
print(f"For s = {sigma_val} + j*{omega_val}:")
if sigma_val < 0:
    print(f"Since σ = {sigma_val} < 0, the signal is STABLE (decays with time)")
elif sigma_val > 0:
    print(f"Since σ = {sigma_val} > 0, the signal is UNSTABLE (grows with time)")
else:
    print(f"Since σ = {sigma_val} = 0, the signal has CONSTANT amplitude (sustained oscillations)")

```

![complex_exponential_sympy](https://github.com/user-attachments/assets/85b898a5-e741-44e6-a695-dd1f1ba97c01)
