# Unit Step Signal

## Definition

The unit step signal is defined as:

$$u(t) = \begin{cases}
1, & \text{if } t \geq 0 \\
0, & \text{if } t < 0
\end{cases}$$

## Utility

The primary utility of the unit step function is to represent instantaneous activation or deactivation of signals.

## Visual Representation and Symbolic Analysis with SymPy

```python
import numpy as np
import matplotlib.pyplot as plt
import sympy as sp
from sympy import symbols, Heaviside, DiracDelta, diff, Piecewise, plot_piecewise

# Define symbolic variables
t = symbols('t', real=True)
a = symbols('a', positive=True)

# Define step function symbolically using Heaviside
unit_step = Heaviside(t)

# Print symbolic representation
print("Unit Step Function (symbolic):")
print(f"u(t) = {unit_step}")

# Define time-shifted variants
delayed_step = Heaviside(t - a)  # Delayed by 'a'
advanced_step = Heaviside(t + a)  # Advanced by 'a'
reflected_step = Heaviside(-t)   # Time reflection

print(f"\nDelayed step u(t-a) = {delayed_step}")
print(f"Advanced step u(t+a) = {advanced_step}")
print(f"Reflected step u(-t) = {reflected_step}")

# Verify that the derivative of the step function is the delta function
step_derivative = diff(unit_step, t)
print(f"\nDerivative of step function: d/dt[u(t)] = {step_derivative}")

# Verify relationship with the delta function
print(f"This confirms: d/dt[u(t)] = δ(t)")

# Numerical visualization
t_vals = np.linspace(-5, 5, 1000)

def step_func(t):
    return np.where(t >= 0, 1, 0)

# Create plots
plt.figure(figsize=(10, 6))
plt.plot(t_vals, step_func(t_vals), 'b-', linewidth=2)
plt.axhline(y=0, color='k', linestyle='-', alpha=0.3)
plt.axvline(x=0, color='k', linestyle='-', alpha=0.3)
plt.grid(True)
plt.title('Unit Step Signal $u(t)$')
plt.xlabel('Time (t)')
plt.ylabel('Amplitude')
plt.ylim(-0.2, 1.2)
plt.tight_layout()
plt.show()

# Plot shifted and reflected functions
plt.figure(figsize=(12, 8))

# Original step
plt.subplot(2, 2, 1)
plt.plot(t_vals, step_func(t_vals), 'b-', linewidth=2)
plt.grid(True)
plt.title('$u(t)$')
plt.ylim(-0.2, 1.2)

# Delayed step (a=2)
plt.subplot(2, 2, 2)
plt.plot(t_vals, step_func(t_vals - 2), 'r-', linewidth=2)
plt.grid(True)
plt.title('$u(t-2)$ (Delayed)')
plt.ylim(-0.2, 1.2)

# Advanced step (a=2)
plt.subplot(2, 2, 3)
plt.plot(t_vals, step_func(t_vals + 2), 'g-', linewidth=2)
plt.grid(True)
plt.title('$u(t+2)$ (Advanced)')
plt.ylim(-0.2, 1.2)

# Reflected step
plt.subplot(2, 2, 4)
plt.plot(t_vals, step_func(-t_vals), 'm-', linewidth=2)
plt.grid(True)
plt.title('$u(-t)$ (Reflected)')
plt.ylim(-0.2, 1.2)

plt.tight_layout()
plt.show()
