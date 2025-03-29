# **Aliasing in Discrete-Time Systems**

![image](https://github.com/user-attachments/assets/28f73f3c-f940-4a1e-8d9e-cfc0a61a26c2)


## **Introduction**

Aliasing is a phenomenon that occurs in discrete-time signal processing when a signal is sampled at an insufficient rate, causing different signals to become indistinguishable from one another. This happens when the sampling theorem is violated, leading to **spectral folding** or **overlapping of frequency components**.

---

## **Understanding Aliasing**

### **Nyquist-Shannon Sampling Theorem**
The **Nyquist-Shannon theorem** states that a continuous-time signal can be perfectly reconstructed from its discrete-time samples **if and only if** the sampling rate satisfies:
$$F_s\geq2F_{\max}$$
where:
- $F_s$ is the sampling frequency (samples per second),
- $F_{\max}$ is the highest frequency component in the signal.

If this condition is not met, aliasing occurs, and different frequency components become indistinguishable in the sampled domain.

### **Mathematical Explanation**
When a continuous-time sinusoidal signal:
$$X(t)=A\cos(2\pi F t)$$
is sampled at a rate $F_s$, the resulting discrete-time signal is:
$$X[n]=A\cos\left(2\pi \frac{F}{F_s} n \right)$$
Aliasing occurs when two different frequencies, $F_1$ and $F_2$, produce the same sampled sequence, meaning:
$$\frac{F_1}{F_s}=\frac{F_2}{F_s}+k,\quad k\in\mathbb{Z}$$
which leads to:
$$F_2=|F_1\pm kF_s|$$
This means that any frequency component beyond $F_s/2$ will appear as a lower frequency, folding back into the range $[0,F_s/2]$.

---

## **Aliasing in the Frequency Domain**

- In the **continuous frequency domain**, the original signal spectrum is centered at $F$.
- After sampling, the discrete-time spectrum **repeats periodically** at multiples of the sampling frequency $F_s$.
- If $F_s$ is too low, adjacent spectral copies **overlap**, making it impossible to distinguish different frequency components.

### **Critical Frequency: The Nyquist Frequency**
The **Nyquist frequency** is defined as:
$$F_N=\frac{F_s}{2}$$
Any frequency component above this value will be **aliased** into the frequency range $[0,F_N]$.

---

## **How to Prevent Aliasing**

1. **Increase the Sampling Rate**
   - Ensure that $F_s\geq2F_{\max}$ to satisfy the Nyquist criterion.

2. **Use an Anti-Aliasing Filter**
   - Before sampling, apply a **low-pass filter** to remove high-frequency components above $F_N$.

3. **Apply Oversampling Techniques**
   - Sample at a much higher rate than required and apply **downsampling** techniques afterward.

---

## **Visualization of Aliasing**
Imagine a spinning wheel in a video. If the frame rate is too low, the wheel may appear to rotate **backward** instead of forward. This is an example of **temporal aliasing**, where the sampling rate (frame rate) is too low to capture the actual motion direction correctly.

---

## **Conclusion**
Aliasing is a fundamental issue in signal processing that arises when the sampling rate is too low. By ensuring a proper sampling rate and using anti-aliasing filters, we can effectively prevent this problem and maintain accurate signal representation in the discrete-time domain.

---
