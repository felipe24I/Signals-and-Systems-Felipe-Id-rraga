<h1 align="center">Exponential Signal</h1>
<p align="center">
  <em>A fundamental signal in signal processing and system analysis</em>
</p>
---

## Definition

The exponential signal is defined as:

$$x(t) = e^{at}$$

Where:
- $a$ is a real constant that determines the behavior of the signal
- $t$ represents time

---

## Behavior

The signal behavior depends on the value of parameter $a$:

- **Decreasing**: When $a < 0$, the signal decreases exponentially over time
- **Increasing**: When $a > 0$, the signal increases exponentially over time

---

## Visual Representation

The exponential signal has two characteristic shapes:

### Increasing exponential ($a > 0$)

![Increasing Exponential Signal](./images/increasing_exponential.png)

- Starts at 1 when $t = 0$
- Grows progressively faster as time increases
- Follows a convex curve upward

### Decreasing exponential ($a < 0$)

![Decreasing Exponential Signal](./images/decreasing_exponential.png)

- Starts at 1 when $t = 0$
- Decreases rapidly at first, then approaches zero asymptotically
- Follows a concave curve approaching the time axis

---

## Applications

The primary utility of exponential signals is modeling natural growth and decay processes, such as:

- Population growth
- Radioactive decay
- Charging/discharging of capacitors
- Temperature changes in thermal systems
- Chemical reactions
- Economic growth or depreciation
- Biological processes

---

## Properties

- Value at $t = 0$ is always 1 (regardless of $a$)
- When $a = 0$, the signal becomes constant: $x(t) = e^0 = 1$
- The exponential signal is the eigenfunction of linear time-invariant systems
- The Laplace transform of $e^{at}$ is $\frac{1}{s-a}$ (for $s > a$)
- The derivative of $e^{at}$ is $a \cdot e^{at}$

---

## Code Example

```python
import numpy as np
import matplotlib.pyplot as plt

# Time vector
t = np.linspace(0, 5, 1000)

# Increasing exponential (a = 1)
a_inc = 1
x_inc = np.exp(a_inc * t)

# Decreasing exponential (a = -1)
a_dec = -1
x_dec = np.exp(a_dec * t)

# Create plots
plt.figure(figsize=(12, 5))

# Increasing exponential
plt.subplot(1, 2, 1)
plt.plot(t, x_inc, 'r-')
plt.grid(True)
plt.title('Increasing Exponential ($a > 0$)')
plt.xlabel('Time (t)')
plt.ylabel('Amplitude')
plt.ylim(0, 150)

# Decreasing exponential
plt.subplot(1, 2, 2)
plt.plot(t, x_dec, 'r-')
plt.grid(True)
plt.title('Decreasing Exponential ($a < 0$)')
plt.xlabel('Time (t)')
plt.ylabel('Amplitude')
plt.ylim(0, 1.1)

plt.tight_layout()
plt.savefig('images/exponential_signals.png', dpi=300)
plt.show()
