# Sinusoidal Signal

## Definition

The sinusoidal signals are defined as:

$$x(t) = \sin(\omega t)$$

$$x(t) = \cos(\omega t)$$

Where:
- $\omega$ is the angular frequency

## Properties

- Periodic functions with angular frequency $\omega$
- 90° phase difference between $\sin(\omega t)$ and $\cos(\omega t)$
- Period: $T = \frac{2\pi}{\omega}$
- Key points for sine wave: 
  - $t = 0$: $\sin(0) = 0$
  - $t = \frac{T}{4}$: $\sin(\frac{\pi}{2}) = 1$
  - $t = \frac{T}{2}$: $\sin(\pi) = 0$
  - $t = \frac{3T}{4}$: $\sin(\frac{3\pi}{2}) = -1$
  - $t = T$: $\sin(2\pi) = 0$

## Visual Representation

```python
import numpy as np
import matplotlib.pyplot as plt
import sympy as sp
from sympy import symbols, sin, cos, pi

# Define symbolic variables
t, omega = symbols('t omega', real=True)

# Define sinusoidal functions symbolically
sine_function = sin(omega * t)
cosine_function = cos(omega * t)

# Print symbolic representation
print("Symbolic sine function:")
print(f"sin(ωt) = {sine_function}")
print("\nSymbolic cosine function:")
print(f"cos(ωt) = {cosine_function}")

# Numerical visualization
omega_val = 2*np.pi  # Using ω=2π for a period of T=1
t_vals = np.linspace(0, 2, 1000)  # 2 periods

# Calculate values
sine_vals = np.sin(omega_val * t_vals)
cosine_vals = np.cos(omega_val * t_vals)

# Create plot
plt.figure(figsize=(10, 6))
plt.plot(t_vals, sine_vals, 'b-', linewidth=2, label='sin(ωt)')
plt.plot(t_vals, cosine_vals, 'r-', linewidth=2, label='cos(ωt)')

# Mark key points (for sine wave)
T = 1  # Period for ω=2π
key_points_t = [0, T/4, T/2, 3*T/4, T]
key_points_sin = [np.sin(omega_val * t) for t in key_points_t]
plt.plot(key_points_t, key_points_sin, 'bo', markersize=6)

# Add labels for key points
labels = ['t=0', 't=T/4', 't=T/2', 't=3T/4', 't=T']
for i, (x, y) in enumerate(zip(key_points_t, key_points_sin)):
    plt.annotate(labels[i], xy=(x, y), xytext=(x+0.02, y+0.1))

# Add vertical lines at key time points
for t_val in key_points_t:
    plt.axvline(x=t_val, color='gray', linestyle='--', alpha=0.3)

# Add pi markers on x-axis
plt.xticks([0, T/4, T/2, 3*T/4, T, 5*T/4, 3*T/2, 7*T/4, 2*T],
           ['0', 'π/2', 'π', '3π/2', '2π', '5π/2', '3π', '7π/2', '4π'])

# Add grid and labels
plt.grid(True)
plt.axhline(y=0, color='k', linestyle='-', alpha=0.3)
plt.title('Sinusoidal Signals')
plt.xlabel('Time (t)')
plt.ylabel('Amplitude')
plt.xlim(0, 2)
plt.ylim(-1.2, 1.2)
plt.legend()
plt.tight_layout()
plt.show()

```

![image](https://github.com/user-attachments/assets/23ad623e-ca74-4cfb-ab94-cd22f92e6a34)

## Utility

Sinusoidal signals represent oscillations and are the foundation of Fourier analysis, which allows complex periodic signals to be decomposed into sums of sinusoids.

## Mathematical Properties

- First derivative: $\frac{d}{dt}[\sin(\omega t)] = \omega \cos(\omega t)$
- Second derivative: $\frac{d^2}{dt^2}[\sin(\omega t)] = -\omega^2 \sin(\omega t)$
- Integration: $\int \sin(\omega t) dt = -\frac{1}{\omega} \cos(\omega t) + C$
- Laplace transform: $\mathcal{L}\{\sin(\omega t)\} = \frac{\omega}{s^2 + \omega^2}$
- Fourier transform: $\mathcal{F}\{\sin(\omega_0 t)\} = \frac{1}{2j}[\delta(\omega-\omega_0) - \delta(\omega+\omega_0)]$

## Relationship to Complex Exponential

Sinusoidal signals can be expressed in terms of complex exponentials using Euler's formula:

$$\sin(\omega t) = \frac{e^{j\omega t} - e^{-j\omega t}}{2j}$$

$$\cos(\omega t) = \frac{e^{j\omega t} + e^{-j\omega t}}{2}$$
