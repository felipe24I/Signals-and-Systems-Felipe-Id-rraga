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

![Delta Function](https://example.com/delta_function.png)

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
