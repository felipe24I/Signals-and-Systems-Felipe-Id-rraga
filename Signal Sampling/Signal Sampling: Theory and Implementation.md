# Signal Sampling: Theory and Implementation

![Sampling Process Diagram](https://github.com/user-attachments/assets/ceb1e903-8654-46f8-af4c-405f4d03ad73)

## Core Definitions
- **Sampling**: Process that discretizes a continuous signal $x(t)$ at regular intervals $T_s$
- **Sampling Frequency ($F_s$)**: Number of samples per second (Hz)
- **Sampling Period ($T_s$)**: Time between samples ($T_s = 1/F_s$)
- **Discrete Time ($t_n$)**: $t_n = n \cdot T_s$ where $n \in \mathbb{Z}$

## Mathematical Representation
The sampled signal can be expressed as:

$$x[n] = x(nT_s) = \sum_{n=-\infty}^\infty x(t) \cdot \delta(t - nT_s)$$

where $\delta(t)$ is the Dirac delta function.

## Nyquist-Shannon Theorem
For perfect reconstruction:
$$F_s > 2F_{max}$$

![Sampling Diagram](https://github.com/user-attachments/assets/6de6dfde-dd1d-4de7-bef0-d83be1de51f7)

## Sample-and-Hold Circuit
![Sample-and-Hold Circuit](https://github.com/user-attachments/assets/6388e3ad-dd69-4907-acb4-287dedf0b6b2)

### Component Functions:
| Component | Role |
|-----------|------|
| **Switch (MOSFET)** | Controls sampling instant |
| **Capacitor (C)** | Stores sampled voltage |
| **Op-Amp** | Provides high impedance buffer |

### Operational Phases:
1. **Sampling Phase (CK HIGH)**:
   - Switch closes
   - Capacitor charges to $V_{in}$
   - Charging time constant: $\tau = R_{on}C$

2. **Hold Phase (CK LOW)**:
   - Switch opens
   - Capacitor maintains voltage
   - Droop rate: $\frac{dV}{dt} = \frac{I_{leakage}}{C}$

## Practical Python Example
```python
import numpy as np
import matplotlib.pyplot as plt

# Parameters
Fs = 1000  # Sampling frequency (Hz)
Ts = 1/Fs  # Sampling period
f = 50     # Signal frequency (Hz)
t = np.linspace(0, 0.1, 1000)  # 100 ms

# Continuous signal
x_cont = np.sin(2*np.pi*f*t)

# Sampled signal
n = np.arange(0, 0.1, Ts)
x_samp = np.sin(2*np.pi*f*n)

# Plot with corrected stem() function
plt.figure(figsize=(10,4))
plt.plot(t, x_cont, 'b-', label='Continuous')
markerline, stemlines, baseline = plt.stem(n, x_samp, 'r-', label='Samples')
plt.setp(markerline, color='red', markersize=5)
plt.setp(stemlines, color='red', linewidth=1)
plt.xlabel('Time (s)'); plt.ylabel('Amplitude')
plt.legend(); plt.grid()
plt.title(f'Signal Sampling (Fs={Fs}Hz, f={f}Hz)')
plt.show()
```
![image](https://github.com/user-attachments/assets/86c02264-1f8d-4225-acbc-960c1f96ed12)

