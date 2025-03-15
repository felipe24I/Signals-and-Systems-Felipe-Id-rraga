# Impulse Signal (Dirac Delta)

## Definition

The Dirac delta impulse signal is defined as:

$$\delta(t) = \begin{cases}
\infty, & t = 0 \\
0, & t \neq 0
\end{cases}$$

For discrete-time signals:

$$\delta[n] = \begin{cases}
1, & n = 0 \\
0, & n \neq 0
\end{cases}$$

## Utility

The primary utility of the delta function is that it allows for obtaining the impulse response of a system.

## Visual Representation

Since the Dirac delta cannot be perfectly represented in digital systems, we approximate it using a narrow pulse with unit area.

```python
import numpy as np
import matplotlib.pyplot as plt

def approximate_delta(t, epsilon=0.1):
    """Approximates the Dirac delta function with a narrow pulse."""
    return np.where(np.abs(t) < epsilon/2, 1/epsilon, 0)

# Time axis for continuous approximation
t = np.linspace(-2, 2, 1000)
delta_approx = approximate_delta(t, epsilon=0.1)

# Discrete delta function
n = np.arange(-5, 6)
delta_discrete = np.zeros_like(n)
delta_discrete[5] = 1  # delta[0] = 1

# Create figure
plt.figure(figsize=(12, 6))

# Plot continuous approximation
plt.subplot(1, 2, 1)
plt.plot(t, delta_approx)
plt.grid(True)
plt.title('Continuous Delta Function Approximation')
plt.xlabel('t')
plt.ylabel('δ(t)')
plt.xlim(-1, 1)

# Plot discrete delta
plt.subplot(1, 2, 2)
plt.stem(n, delta_discrete)
plt.grid(True)
plt.title('Discrete Delta Function')
plt.xlabel('n')
plt.ylabel('δ[n]')
plt.xlim(-6, 6)

plt.tight_layout()
plt.show()

## Characteristics

- It is a **generalized function** (acts by extracting the value of a function at a specific point)

## Properties

### Fundamental Properties

- **Unit area**: 
  $$\int_{-\infty}^{\infty} \delta(t) dt = 1$$

- **Sampling (sifting) property**: 
  $$\int_{-\infty}^{\infty} \delta(t-t_0)x(t) dt = x(t_0)$$

- **Multiplication property**: 
  $$x(t) \cdot \delta(t-t_0) = x(t_0) \delta(t-t_0)$$

### Additional Properties

- **Parity**: It is an even function
  $$\delta(-t) = \delta(t)$$

- **Scaling property**: 
  $$\delta(at) = \frac{1}{|a|} \delta(t), \text{ for } a \neq 0$$

- **Linearity**: 
  $$a \cdot \delta(t) + b \cdot \delta(t) = (a+b) \cdot \delta(t)$$

- **Derivative relation**: 
  $$\int_{-\infty}^{\infty} \frac{d\delta(t)}{dt} \cdot x(t) dt = -\left.\frac{dx(t)}{dt}\right|_{t=0}$$

- **Unit step derivative**: 
  $$\delta(t) = \frac{du(t)}{dt}$$

- **Sign function relation**: 
  $$\frac{d\text{sgn}(t)}{dt} = 2\delta(t)$$

- **Convolution property**: 
  $$f(t) * \delta(t-t_0) = f(t-t_0)$$

- **Fourier transform**: 
  $$\mathcal{F}\{\delta(t)\} = 1$$

- **Laplace transform**: 
  $$\mathcal{L}\{\delta(t)\} = 1$$
