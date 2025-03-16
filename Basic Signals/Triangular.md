# Triangular Signal

## Definition

The triangular signal is defined as:

$$tri(t) = \begin{cases}
1 - |t|, & \text{if } -1 \leq t \leq 1 \\
0, & \text{if } t > 1 \\
0, & \text{if } t < -1
\end{cases}$$

## General Form

A more general form with arbitrary center, width, and amplitude:

$$A \cdot tri\left(\frac{t-t_0}{w}\right) = \begin{cases}
A \cdot \left(1 - \left|\frac{t-t_0}{w}\right|\right), & \text{if } t_0-w \leq t \leq t_0+w \\
0, & \text{otherwise}
\end{cases}$$

Where:
- $t_0$ → center of the triangle
- $2w$ → total width of the triangle
- $w$ → half-width of the triangle base
- $A$ → amplitude of the triangle

The slope of the sides is $\pm \frac{A}{w}$

## Visual Representation

```python
import numpy as np
import matplotlib.pyplot as plt
import sympy as sp
from sympy import symbols, Piecewise, Abs

# Define symbolic variables
t, t0, w, A = symbols('t t0 w A', real=True)

# Define triangular function symbolically
tri_function = Piecewise((1 - Abs(t), (t >= -1) & (t <= 1)), (0, True))

# Print symbolic representation
print("Symbolic triangular function:")
print(f"tri(t) = {tri_function}")

# Define generalized triangular function
gen_tri = Piecewise((A*(1 - Abs((t-t0)/w)), ((t >= t0-w) & (t <= t0+w))), (0, True))
print("\nGeneralized triangular function:")
print(f"A·tri((t-t0)/w) = {gen_tri}")

# Numerical visualization
t_vals = np.linspace(-3, 3, 1000)

# Standard triangular function
def tri(t):
    return np.maximum(0, 1 - np.abs(t))

# Generalized triangular function
def gen_tri(t, t0, w, A):
    return np.where(
        (t >= t0-w) & (t <= t0+w),
        A * (1 - np.abs((t-t0)/w)),
        0
    )

# Create plots
fig, (ax1, ax2) = plt.subplots(2, 1, figsize=(10, 8))

# Standard triangular function
ax1.plot(t_vals, tri(t_vals), 'b-', linewidth=2)
ax1.grid(True)
ax1.axhline(y=0, color='k', linestyle='-', alpha=0.3)
ax1.axvline(x=0, color='k', linestyle='-', alpha=0.3)
ax1.set_title('Standard Triangular Signal: tri(t)')
ax1.set_xlabel('Time (t)')
ax1.set_ylabel('Amplitude')
ax1.set_ylim(-0.2, 1.2)
ax1.set_xlim(-3, 3)

# Key points for standard triangular
ax1.plot([-1, 0, 1], [0, 1, 0], 'ro', markersize=5)
ax1.annotate('-1', xy=(-1, 0), xytext=(-1, -0.1), ha='center')
ax1.annotate('0', xy=(0, 1), xytext=(0, 1.1), ha='center')
ax1.annotate('1', xy=(1, 0), xytext=(1, -0.1), ha='center')

# Generalized triangular function
t0_val = 0.5  # Center shifted to 0.5
w_val = 0.8   # Half-width
A_val = 1.2   # Amplitude

ax2.plot(t_vals, gen_tri(t_vals, t0_val, w_val, A_val), 'r-', linewidth=2)
ax2.grid(True)
ax2.axhline(y=0, color='k', linestyle='-', alpha=0.3)
ax2.axvline(x=t0_val, color='k', linestyle='-', alpha=0.3)
ax2.set_title(f'Generalized Triangular Signal: A·tri((t-t₀)/w) with t₀={t0_val}, w={w_val}, A={A_val}')
ax2.set_xlabel('Time (t)')
ax2.set_ylabel('Amplitude')
ax2.set_ylim(-0.2, A_val*1.2)
ax2.set_xlim(-3, 3)

# Key points and annotations for generalized triangular
left_edge = t0_val - w_val
right_edge = t0_val + w_val
ax2.plot([left_edge, t0_val, right_edge], [0, A_val, 0], 'ko', markersize=5)
ax2.annotate('t₀-w', xy=(left_edge, 0), xytext=(left_edge, -0.1), ha='center')
ax2.annotate('t₀', xy=(t0_val, A_val), xytext=(t0_val, A_val*1.1), ha='center')
ax2.annotate('t₀+w', xy=(right_edge, 0), xytext=(right_edge, -0.1), ha='center')
ax2.annotate('2w', xy=(t0_val, -0.1), xytext=(t0_val, -0.2), ha='center')
ax2.annotate('', xy=(left_edge, -0.1), xytext=(right_edge, -0.1),
             arrowprops=dict(arrowstyle='<->'))

plt.tight_layout()
plt.show()
