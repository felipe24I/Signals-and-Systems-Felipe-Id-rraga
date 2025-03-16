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
from sympy import symbols, Heaviside, DiracDelta, diff, Piecewise

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
reflected_step2 = -Heaviside(t) #Amplitude reflection
reflected_step3 = -Heaviside(-t) #Phase reflection

# Print time-shifted variants
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

```

![image](https://github.com/user-attachments/assets/e3fad82f-f18f-4548-88cd-780ea0cbb2f2)

```python
# Plot shifted and reflected functions
plt.figure(figsize=(12, 8))

# Amplitude reflection
plt.subplot(2, 2, 1)
plt.plot(t_vals, -step_func(t_vals), 'b-', linewidth=2)
plt.grid(True)
plt.title('$-u(t)$')
plt.ylim(-1.2, 1.2)

# Amplitude and time reflection
plt.subplot(2, 2, 2)
plt.plot(t_vals, -step_func(-t_vals), 'r-', linewidth=2)
plt.grid(True)
plt.title('$-u(-t)$')
plt.ylim(-1.2, 1.2)

```

![image](https://github.com/user-attachments/assets/9ba21ad0-8062-4fc8-8132-f75b0a61659a)

# Properties
Time Reflection Properties
Reflection of the independent variable:
If we reflect the time axis with u(−t)u(-t)
u(−t), we get:

$$u(-t) = \begin{cases}
0, & \text{if } -t < 0 \Rightarrow t > 0 \
1, & \text{if } -t \geq 0 \Rightarrow t \leq 0
\end{cases}$$
Reflection of the dependent variable:
If we negate the amplitude with −u(t)-u(t)
−u(t), we get:

$$-u(t) = \begin{cases}
-1, & \text{if } t \geq 0 \
0, & \text{if } t < 0
\end{cases}$$
Note: The unit step function u(t)u(t)
u(t) always takes values of either 0 or 1. Therefore, −u(t)-u(t)
−u(t) will be either 0 or -1.

Time-Shifted Step Functions
Delayed signal u(t−a)u(t-a)
u(t−a) where a>0a > 0
a>0:
$$u(t-a) = \begin{cases}
0, & \text{if } t-a < 0 \Rightarrow t < a \
1, & \text{if } t-a \geq 0 \Rightarrow t \geq a
\end{cases}$$
This represents a step that is "delayed" by aa
a seconds because it activates at t=at = a
t=a instead of t=0t = 0
t=0.

Advanced signal u(t+a)u(t+a)
u(t+a) where a>0a > 0
a>0:
$$u(t+a) = \begin{cases}
0, & \text{if } t+a < 0 \Rightarrow t < -a \
1, & \text{if } t+a \geq 0 \Rightarrow t \geq -a
\end{cases}$$
This represents a step that is "advanced" by aa
a seconds because it activates at t=−at = -a
t=−a instead of t=0t = 0
t=0.
