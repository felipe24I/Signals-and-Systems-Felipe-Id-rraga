# Sinc Signal

## Definition

The sinc signal is defined as:

$$x(t) = \operatorname{sinc}(t) = \frac{\sin(\pi t)}{\pi t}$$

## Visual Representation

```python
import numpy as np
import matplotlib.pyplot as plt
import sympy as sp
from sympy import symbols, sin, pi

# Define symbolic variables
t = symbols('t', real=True)

# Define sinc function symbolically
sinc_function = sin(pi * t) / (pi * t)

# Print symbolic representation
print("Symbolic sinc function:")
print(f"sinc(t) = {sinc_function}")

# Handle the singularity at t=0 for symbolic evaluation
sinc_at_zero = sp.limit(sinc_function, t, 0)
print(f"Value at t=0: sinc(0) = {sinc_at_zero}")

# Numerical visualization
t_vals = np.linspace(-5, 5, 1000)

# Define numpy's sinc function (note: numpy's sinc already includes the division by pi)
def sinc(t):
    return np.sinc(t)  # numpy's sinc is defined as sin(πx)/(πx)

# Plot the sinc function
plt.figure(figsize=(10, 6))
plt.plot(t_vals, sinc(t_vals), 'b-', linewidth=2)

# Add grid and labels
plt.grid(True)
plt.axhline(y=0, color='k', linestyle='-', alpha=0.3)
plt.axvline(x=0, color='k', linestyle='-', alpha=0.3)
plt.title('Sinc Signal: $\\operatorname{sinc}(t) = \\frac{\\sin(\\pi t)}{\\pi t}$')
plt.xlabel('Time (t)')
plt.ylabel('Amplitude')

# Mark key points
plt.plot(0, 1, 'ro', markersize=6)  # sinc(0) = 1
plt.annotate('sinc(0) = 1', xy=(0, 1), xytext=(0.2, 1.1))

zeros = np.arange(1, 6)
for n in zeros:
    plt.plot(n, 0, 'ro', markersize=4, alpha=0.7)
    plt.plot(-n, 0, 'ro', markersize=4, alpha=0.7)
    
plt.annotate('Zeros at t = ±n, n ∈ ℤ⁺', xy=(1, 0), xytext=(1.5, 0.2),
             arrowprops=dict(facecolor='red', shrink=0.05))

plt.xlim(-5, 5)
plt.ylim(-0.3, 1.1)
plt.tight_layout()
plt.show()

```

## Utility

The sinc function appears in signal sampling and reconstruction. It is the Fourier transform of the rectangular function and plays a fundamental role in the sampling theorem and signal interpolation.

## Properties

- **Value at origin**: $\operatorname{sinc}(0) = 1$ (using L'Hôpital's rule)
- **Zeros**: $\operatorname{sinc}(n) = 0$ for all non-zero integers $n$
- **Symmetry**: $\operatorname{sinc}(-t) = \operatorname{sinc}(t)$ (even function)
- **Fourier transform**: $\mathcal{F}\{\operatorname{sinc}(t)\} = \text{rect}(f)$ (rectangular function)
- **Decaying oscillations**: The function oscillates with decreasing amplitude as $|t|$ increases

## Applications

- Ideal lowpass filter response
- Signal reconstruction in the sampling theorem
- Interpolation of discrete data points
- Image processing and reconstruction
- Digital filter design
