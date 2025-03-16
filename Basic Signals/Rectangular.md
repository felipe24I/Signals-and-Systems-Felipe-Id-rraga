# Rectangular Signal

## Definition

The rectangular signal with parameter $\tau$ is defined as:

$$rect_\tau(t) = \begin{cases}
1, & -\tau < t < \tau \\
0, & \text{otherwise}
\end{cases}$$

## Visual Representation

```python
import numpy as np
import matplotlib.pyplot as plt
import sympy as sp
from sympy import symbols, Piecewise

# Define symbolic variables
t, tau = symbols('t tau', real=True)

# Define rectangular function symbolically
rect_function = Piecewise((1, (t > -tau) & (t < tau)), (0, True))

# Print symbolic representation
print("Symbolic rectangular function:")
print(f"rect_τ(t) = {rect_function}")

# Numerical visualization
tau_val = 0.5  # Half-width of rectangle
t_vals = np.linspace(-2, 2, 1000)

# Rectangular function
def rect(t, tau):
    return np.where((t > -tau) & (t < tau), 1, 0)

# Create plot
plt.figure(figsize=(10, 6))
plt.plot(t_vals, rect(t_vals, tau_val), 'r-', linewidth=2)

# Add key points and labels
plt.plot([-tau_val, tau_val], [1, 1], 'ko', markersize=5)
plt.annotate('-τ', xy=(-tau_val, 0), xytext=(-tau_val, -0.1), ha='center')
plt.annotate('τ', xy=(tau_val, 0), xytext=(tau_val, -0.1), ha='center')
plt.annotate('Width = 2τ', xy=(0, 0.5), xytext=(0, 0.6), ha='center')

# Add grid and labels
plt.grid(True)
plt.axhline(y=0, color='k', linestyle='-', alpha=0.3)
plt.axvline(x=0, color='k', linestyle='-', alpha=0.3)
plt.title('Rectangular Signal')
plt.xlabel('Time (t)')
plt.ylabel('Amplitude')
plt.ylim(-0.2, 1.2)
plt.xlim(-2, 2)
plt.tight_layout()
plt.show()

```

## Properties

- **On and off**: Represents a signal that is active for a specific time window
- **Utility**: Models temporal windows in signal processing
- **Area**: The area of the rectangle is 2τ (height × width = 1 × 2τ = 2τ)
- **Relationship with step function**: $rect(t) = u(t + \frac{\tau}{2}) - u(t - \frac{\tau}{2})$
- **Limiting behavior**: $\lim_{\tau \to 0} rect_\tau(t) = \delta(t)$
  - As τ becomes very small, the rectangle approaches the delta function while maintaining unit area

## Mathematical Representation

For the standard rectangular signal with height 1 and width 2τ:

$$Area = base \cdot height = 2\tau \cdot 1 = 2\tau$$

For a normalized rectangular pulse with area 1, the height would be adjusted to 1/(2τ):

$$Area = base \cdot height = 2\tau \cdot \frac{1}{2\tau} = 1$$
