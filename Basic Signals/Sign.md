
# Sign Signal

## Definition

The sign function (or signum function) is defined as:

$$sgn(t) = \begin{cases}
1, & t > 0 \\
0, & t = 0 \\
-1, & t < 0
\end{cases}$$

## Visual Representation

```python
import numpy as np
import matplotlib.pyplot as plt
import sympy as sp
from sympy import symbols, sign, Piecewise

# Define symbolic variables
t = symbols('t', real=True)

# Define sign function symbolically
sign_function = Piecewise((1, t > 0), (0, t == 0), (-1, t < 0))

# Print symbolic representation
print("Symbolic sign function:")
print(f"sgn(t) = {sign_function}")

# Numerical visualization
t_vals = np.linspace(-3, 3, 1000)

# Sign function
def sgn(t):
    return np.sign(t)

# Create plot
plt.figure(figsize=(10, 6))
plt.plot(t_vals, sgn(t_vals), 'b-', linewidth=2)

# Add key points
plt.plot(0, 0, 'ko', markersize=6)

# Add grid and labels
plt.grid(True)
plt.axhline(y=0, color='k', linestyle='-', alpha=0.3)
plt.axvline(x=0, color='k', linestyle='-', alpha=0.3)
plt.title('Sign Function: sgn(t)')
plt.xlabel('Time (t)')
plt.ylabel('Amplitude')
plt.ylim(-1.5, 1.5)
plt.xlim(-3, 3)

# Add annotations
plt.annotate('sgn(t) = 1 for t > 0', xy=(1.5, 1), xytext=(1.5, 1.2))
plt.annotate('sgn(t) = -1 for t < 0', xy=(-1.5, -1), xytext=(-1.5, -1.2))
plt.annotate('sgn(0) = 0', xy=(0, 0), xytext=(0.2, 0.2),
             arrowprops=dict(facecolor='black', shrink=0.05))

plt.tight_layout()
plt.show()

```

![image](https://github.com/user-attachments/assets/ec5d278d-bda9-4b00-b30d-5178acd0a649)

## Utility

The sign function is useful for representing the absolute value of a real signal X(t):

$$|X(t)| = X(t) \cdot sgn(X(t))$$

## Relationship with Unit Step Function

The sign function can be expressed in terms of the unit step function:

$$sgn(t) = 2u(t) - 1$$
