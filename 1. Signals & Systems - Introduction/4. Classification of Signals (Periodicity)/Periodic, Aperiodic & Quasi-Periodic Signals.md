# Periodic, Aperiodic & Quasi-Periodic Signals

![image](https://github.com/user-attachments/assets/6521884b-d974-4323-b1b4-a834de592a74)

## Concepts to Know  

- **Angular Frequency:**  
  $$\omega = 2\pi F \quad \left[\frac{\text{rad}}{s}\right]$$
  
- **Angle (Phase):**  
  $$\theta = \omega t \quad [\text{rad}]$$
  
  Thus,  
  $$\sin(\omega t) = \sin(\theta(t))$$  
  The angle is a function of time.

- **Period (T):** The time a phasor takes to complete a full cycle.  
  $$T = \frac{1}{F}$$
  
  Thus,  
  $$\omega = \frac{2\pi}{T}$$

## Periodicity  

- A function **X(t) is periodic** if:  
  $X(t \pm T) = X(t)$  
  for some **minimum positive** $T$, called the **fundamental period**.

## Examples:  
![image](https://github.com/user-attachments/assets/2de9761e-d5f8-48db-9532-951fb44e5eec)  

## Periods of $\sin(\omega t)$ and $\cos(\omega t)$  

- The **fundamental period** of $\sin(\omega t)$ and $\cos(\omega t)$ is:  
  $T = \frac{2\pi}{\omega}$  

## Periodic Function Transformations  

1. **Scaling the argument of a periodic function**:  
   - If $T$ is the period of a periodic function $f(\omega t)$, then:  
     $f(a\omega t + b)$  
     where $a > 0$, is also periodic with period:  
     $T' = \frac{T}{|a|}$  
     
   - Example: The period of $\sin(a\omega t + b)$ and $\cos(a\omega t + b)$ is:  
     $T = \frac{2\pi}{|a|}$  

2. **Multiplying a periodic function by a constant**:  
   - If $T$ is the period of $f(\omega t)$, then:  
     $a f(\omega t + b)$  
     where $a > 0$, remains periodic **with the same period $T$**.  

   - Example: The period of $a\sin(\omega t + b)$ and $a\cos(\omega t + b)$ is:  
     $T = \frac{2\pi}{\omega}$  

---

## **Exercise**  

**Prove that the following functions are periodic:**  

1. $X(t) = \cos(\omega t)$, where $\omega \in \mathbb{R}^+$  
2. $X(t) = \sin(\omega t)$, where $\omega \in \mathbb{R}^+$  

---

## **Solution**  

### **1. Proof for $\cos(\omega t)$**  

We need to show that:  
$\cos(\omega (t \pm T)) = \cos(\omega t)$  

#### **Step 1: Using the trigonometric identity**  
$\cos(\alpha \pm \beta) = \cos(\alpha)\cos(\beta) \mp \sin(\alpha)\sin(\beta)$  
where:  
- $\alpha = \omega t$  
- $\beta = \omega T$  

#### **Step 2: Substituting values**  
$\cos(\omega t \pm \omega T) = \cos(\omega t) \cos(\omega T) \mp \sin(\omega t) \sin(\omega T)$  

Since we know that for the **fundamental period** $T = \frac{2\pi}{\omega}$:  
$\cos(\omega T) = \cos(2\pi) = 1$  
$\sin(\omega T) = \sin(2\pi) = 0$  

#### **Step 3: Simplifying**  
$\cos(\omega t \pm \omega T) = \cos(\omega t) \cdot 1 \mp \sin(\omega t) \cdot 0$  
$\cos(\omega t \pm \omega T) = \cos(\omega t)$  

Thus, **$X(t) = \cos(\omega t)$ is periodic with period $T = \frac{2\pi}{\omega}$.** ✅  

---

### **2. Proof for $\sin(\omega t)$**  

We need to show that:  
$\sin(\omega (t \pm T)) = \sin(\omega t)$  

#### **Step 1: Using the trigonometric identity**  
$\sin(\alpha \pm \beta) = \sin(\alpha)\cos(\beta) \pm \cos(\alpha)\sin(\beta)$  
where:  
- $\alpha = \omega t$  
- $\beta = \omega T$  

#### **Step 2: Substituting values**  
$\sin(\omega t \pm \omega T) = \sin(\omega t) \cos(\omega T) \pm \cos(\omega t) \sin(\omega T)$  

Since for $T = \frac{2\pi}{\omega}$:  
$\cos(\omega T) = \cos(2\pi) = 1, \quad \sin(\omega T) = \sin(2\pi) = 0$  

#### **Step 3: Simplifying**  
$\sin(\omega t \pm \omega T) = \sin(\omega t) \cdot 1 \pm \cos(\omega t) \cdot 0$  
$\sin(\omega t \pm \omega T) = \sin(\omega t)$  

Thus, **$X(t) = \sin(\omega t)$ is periodic with period $T = \frac{2\pi}{\omega}$.**

# Aperiodic Signals  

## Definition  

- A signal $X(t)$ is **aperiodic** if it **does not satisfy** the periodicity condition:  
  $X(t \pm T) \neq X(t) \quad \forall T > 0$  
- This means that **there is no finite period** $T$ such that the function repeats itself.  

## Examples  

Some common **aperiodic signals** include:  

1. **Exponential Decay Function**  
   $X(t) = e^{-at}, \quad a > 0$  

$f(n) = \begin{cases} 1, & t = 0 \\ 0, & t = 1 \end{cases}$

**Unit Step Function**  

| Condition | Value |
|-----------|-------|
| $t \geq 0$ | 1 |
| $t < 0$ | 0 |


4. **Ramp Function**  
   $X(t) = t u(t)$  

## Characteristics of Aperiodic Signals  

- **No repeating pattern**: The signal does not return to the same value after a fixed interval.  
- **Fourier Transform exists**: Unlike periodic signals, aperiodic signals are typically analyzed using the **Fourier Transform**, which provides their frequency content.  
- **Finite or infinite duration**: Some aperiodic signals exist for all time (e.g., exponential decay), while others are defined over a finite interval (e.g., rectangular pulse).  

## Relationship to Periodic Signals  

- A **periodic signal** can be seen as an **infinite repetition** of an aperiodic signal.  
- Conversely, an **aperiodic signal** can be considered as a **single period** of an infinitely extended periodic function.  
- This relationship is essential in Fourier analysis, where the **Fourier series** of a periodic signal leads to the **Fourier Transform** of an aperiodic signal when the period tends to infinity.  

## Example Problem  

### **Given:**  
A signal is defined as:  
$X(t) = e^{-2t} u(t)$  
where $u(t)$ is the unit step function.  

**Question:** Prove that $X(t)$ is aperiodic.  

### **Solution:**  
1. Suppose $X(t)$ is periodic, meaning there exists a period $T$ such that:  
   $X(t + T) = X(t)$  
   for all $t$.  

2. Substituting $X(t) = e^{-2t} u(t)$ into this equation:  
   $e^{-2(t+T)} u(t+T) = e^{-2t} u(t)$  

3. Dividing both sides by $e^{-2t}$ (for $t \geq 0$):  
   $e^{-2T} = 1$  

4. The only solution to this equation is $T = 0$, which contradicts the assumption that $T > 0$.  

5. **Conclusion**: Since no nonzero period exists, **$X(t)$ is aperiodic**.
