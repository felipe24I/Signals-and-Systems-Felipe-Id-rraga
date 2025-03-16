# Ramp Signal

## Definition

The ramp signal is defined as:

$$x(t) = \alpha t \cdot u(t)$$

Where:
- $\alpha$ controls the slope (growth rate)
- $u(t)$ is the unit step function

## Visual Representation

```python
import numpy as np
import matplotlib.pyplot as plt

# Time axis
t = np.linspace(-2, 5, 1000)

# Function to generate ramp signal
def ramp(t, alpha=1):
    return alpha * t * np.where(t >= 0, 1, 0)

# Create different ramp signals
fig, ax = plt.subplots(figsize=(10, 6))

# Steep ramp (α > 1)
ax.plot(t, ramp(t, alpha=2), 'r-', linewidth=2, label='α > 1 (Steep slope)')

# Standard ramp (α = 1)
ax.plot(t, ramp(t, alpha=1), 'b-', linewidth=2, label='α = 1 (Standard slope)')

# Gentle ramp (0 < α < 1)
ax.plot(t, ramp(t, alpha=0.5), 'g-', linewidth=2, label='0 < α < 1 (Gentle slope)')

# Negative ramp (α < 0)
ax.plot(t, ramp(t, alpha=-1), 'm-', linewidth=2, label='α < 0 (Negative slope)')

# Add grid and labels
ax.grid(True)
ax.axhline(y=0, color='k', linestyle='-', alpha=0.3)
ax.axvline(x=0, color='k', linestyle='-', alpha=0.3)
ax.set_title('Ramp Signals with Different Slopes')
ax.set_xlabel('Time (t)')
ax.set_ylabel('Amplitude')
ax.legend()
plt.tight_layout()
plt.show()

```
