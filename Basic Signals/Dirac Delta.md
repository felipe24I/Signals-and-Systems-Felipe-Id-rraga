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

```
![Dirac Delta](https://github.com/user-attachments/assets/6fe1a212-e0a5-4701-879a-3c074e2ed187)

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

---

## Mathematical Proofs

### Proof of the Sampling Property

Starting with $\delta(t-t_0)x(t) = \delta(t-t_0)x(t_0)$ (due to the definition of delta and its graphical representation):

$$\int_{-\infty}^{\infty} \delta(t-t_0)x(t) dt = \int_{-\infty}^{\infty} \delta(t-t_0)x(t_0) dt$$

$$\int_{-\infty}^{\infty} \delta(t-t_0)x(t) dt = x(t_0) \int_{-\infty}^{\infty} \delta(t-t_0) dt$$

$$\int_{-\infty}^{\infty} \delta(t-t_0)x(t) dt = x(t_0) \cdot 1$$

$$\int_{-\infty}^{\infty} \delta(t-t_0)x(t) dt = x(t_0)$$

### Proof of the Scaling Property

To evaluate $\int_{-\infty}^{\infty} \delta(at) dt$ for $a \neq 0$, we use the substitution:

$t' = at$
$dt' = a \cdot dt$

#### Case 1: When $a < 0$

By properties of integrals with changes of limits:

$$\int_{-\infty}^{\infty} \delta(t') \frac{dt'}{a} = -\frac{1}{a}\int_{-\infty}^{\infty} \delta(t') dt' = -\frac{1}{a} \cdot 1 = -\frac{1}{a}$$

Since $a < 0$, this gives $\frac{1}{|a|}$

#### Case 2: When $a > 0$

The limits transform as:
- When $t = -\infty$, $t' = -\infty$
- When $t = \infty$, $t' = \infty$

Therefore:

$$\int_{-\infty}^{\infty} \delta(t') \frac{dt'}{a} = \frac{1}{a}\int_{-\infty}^{\infty} \delta(t') dt' = \frac{1}{a} \cdot 1 = \frac{1}{a}$$

#### Combined Result

For both cases, we can write:

$$\int_{-\infty}^{\infty} \delta(at) dt = \frac{1}{|a|}$$

Which means:

$$\delta(at) = \frac{1}{|a|}\delta(t)$$

### Proof of the Derivative Property

To prove: $\int_{-\infty}^{\infty} \frac{d\delta(t)}{dt} \cdot x(t) dt = -\left.\frac{dx(t)}{dt}\right|_{t=0}$

Using integration by parts with:
- $u = x(t)$
- $dv = \frac{d\delta(t)}{dt} dt$
- $du = \frac{dx(t)}{dt} dt$
- $v = \delta(t)$

We get:

$$\int_{-\infty}^{\infty} \frac{d\delta(t)}{dt} \cdot x(t) dt = $$

Since $\delta(\infty) = \delta(-\infty) = 0$:

$$\int_{-\infty}^{\infty} \frac{d\delta(t)}{dt} \cdot x(t) dt = 0 - \int_{-\infty}^{\infty} \delta(t) \frac{dx(t)}{dt} dt$$

Applying the sampling property:

$$\int_{-\infty}^{\infty} \frac{d\delta(t)}{dt} \cdot x(t) dt = -\left.\frac{dx(t)}{dt}\right|_{t=0}$$

### Proof with Shifted Derivative

For $\int_{-\infty}^{\infty} \frac{d\delta(t \pm t_0)}{dt} \cdot x(t) dt$:

Using integration by parts with:
- $u = x(t)$
- $dv = \frac{d\delta(t \pm t_0)}{dt} dt$
- $du = \frac{dx(t)}{dt} dt$
- $v = \delta(t \pm t_0)$

We get:

$$\int_{-\infty}^{\infty} \frac{d\delta(t \pm t_0)}{dt} \cdot x(t) dt = x(t)\delta(t \pm t_0)\big|_{-\infty}^{\infty} - \int_{-\infty}^{\infty} \delta(t \pm t_0) \frac{dx(t)}{dt} dt$$

Since $\delta(\infty \pm t_0) = \delta(-\infty \pm t_0) = 0$:

$$\int_{-\infty}^{\infty} \frac{d\delta(t \pm t_0)}{dt} \cdot x(t) dt = - \int_{-\infty}^{\infty} \delta(t \pm t_0) \frac{dx(t)}{dt} dt$$

Applying the sampling property:

$$\int_{-\infty}^{\infty} \frac{d\delta(t \pm t_0)}{dt} \cdot x(t) dt = -\left.\frac{dx(t)}{dt}\right|_{t=\mp t_0}$$

## Notes about Even Functions

- Remember that an even function is a mathematical function that satisfies $f(x) = f(-x)$ for all x in its domain
- Examples: $f(x) = x^2$ is symmetric with respect to the y-axis
- The delta function is an even function: $\delta(t) = \delta(-t)$
