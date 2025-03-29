# **Discrete-Time Periodicity**

## **Key Concept Reminder**

- Time in discrete systems is represented as:
  $$
  t = nT_s, \quad n \in \mathbb{Z}
  $$
  where $T_s$ is the sampling period.

- Expressing a cosine function in terms of discrete time:
  $$
  \cos[\omega nT_s] = \cos\left[\frac{2\pi}{T} nT_s\right]
  $$
  $$
  \cos[\omega nT_s] = \cos\left[2\pi F \frac{n}{F_s}\right]
  $$
  $$
  \cos[\omega nT_s] = \cos\left[2\pi \frac{F}{F_s} n\right]
  $$

- **Frequency interpretation in discrete time:**
  $$
  f = \frac{F}{F_s} \quad \Rightarrow \quad \text{frecuencia en ciclos por muestra}
  $$
  In other words, **how many samples represent one cycle**.

- The **angle** in discrete time as a function of samples:
  $$
  \theta[n] = 2\pi f n
  $$

---

## **Angular Frequency in Discrete Time**

- In discrete-time signals, we define the angular frequency as:
  $$
  \Omega = 2\pi \frac{F}{F_s}, \quad \left[\frac{\text{radianes}}{\text{muestra}}\right]
  $$
  Thus, a discrete-time cosine signal is written as:
  $$
  \cos [\Omega n]
  $$

---

# **Periodicity Condition in Discrete Time**

For a discrete-time signal to be **periodic**, it must satisfy:
$$
\cos[\Omega n] = \cos[\Omega (n \pm N)]
$$
where $ N $ is the **period (number of samples per cycle)**.

### **Period Formula in Discrete Time**

- Since frequency is defined as:
  $$
  f = \frac{F}{F_s}
  $$
  and for periodicity in discrete time:
  $$
  N = \frac{1}{f} = \frac{F_s}{F}
  $$

Thus, the signal is periodic **if and only if $ N $ is an integer**.

---

## **Exercise: Proof of Periodicity**

### **Given Signal**
$$
X[n] = \cos[\Omega n]
$$
Prove that $ X[n] $ is periodic.

### **Solution**

We start with the periodicity condition:
$$
\cos[\Omega n] = \cos[\Omega (n \pm N)]
$$

Substituting $ \Omega = 2\pi f $:
$$
\cos[\Omega n] = \cos[2\pi f (n \pm N)]
$$

Using the identity:
$$
\cos(\alpha \pm \beta) = \cos(\alpha)\cos(\beta) \mp \sin(\alpha)\sin(\beta)
$$
where:
- $ \alpha = 2\pi f n $
- $ \beta = 2\pi f N $

Applying the trigonometric identity:
$$
\cos(2\pi f n \pm 2\pi f N ) = \cos(2\pi f n)\cos(2\pi f N) \mp \sin(2\pi f n)\sin(2\pi f N)
$$

Since:
$$
\cos(2\pi f N) = 1, \quad \sin(2\pi f N) = 0
$$

we get:
$$
\cos(2\pi f n \pm 2\pi f N ) = \cos(2\pi f n)
$$

which confirms:
$$
\cos[\Omega (n \pm N)] = \cos[\Omega n]
$$

Thus, the signal is **periodic if and only if $ N $ is an integer**.

---

### **Key Takeaway**
- A discrete-time signal is **periodic** if its period $ N $ is an **integer**.
- The relationship between frequency and period is:
  $$
  N = \frac{F_s}{F}
  $$
  where $ F $ is the frequency in continuous time and $ F_s $ is the sampling frequency.

---
