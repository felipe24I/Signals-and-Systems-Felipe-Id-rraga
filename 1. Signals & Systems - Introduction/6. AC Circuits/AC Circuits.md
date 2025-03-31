# AC circuits

![image](https://github.com/user-attachments/assets/b7ab8ffd-ad6f-415a-9d9a-d30c1bc14095)

## Voltages

$v(t)= v_m\sin(\omega t + \theta_v) [V]$

$v(t)= v_m\cos(\omega t + \theta_v) [V]$

## Currents

$i(t)= i_m\sin(\omega t + \theta_i) [A]$

$i(t)= i_m\cos(\omega t + \theta_i) [A]$

## Impedances

| Element          | Rectangular Form $(Z=R+jX)$       | Polar Form $(Z=∣Z∣∠θ)$                       | Angle $(\theta)$ |
|------------------|------------------------------|----------------------------------------|------------------|
| **Resistor (R)** |   $R + j0 $                  | $R \angle 0^\circ$                     | $0^\circ$        |
| **Inductor (L)** |   $0 + j\omega L$            | $\omega L \angle 90^\circ$             | $+90^\circ$      |
| **Capacitor (C)**|   $0 - j\frac{1}{\omega C}$  | $\frac{1}{\omega C} \angle -90^\circ$  | $-90^\circ$      |

## Impedance Form Conversions

## 1. Rectangular to Polar Conversion

$\vert Z \vert = \sqrt{R^2 + X^2}$,  $\theta =\tan^{-1}(\frac{X}{R})$

- **For example:** $Z = 3 + j4\Omega \rightarrow 5\angle 53.1^\circ$

## 2. Polar to Rectangular Conversion

$R = \vert Z \vert \cos\theta$,  $X=\vert Z \vert \sin\theta$

- **For example:** $10\angle 30^\circ \rightarrow 8.66 + j5\Omega$

---

# $\sin(\omega t)$ and $\cos(\omega t)$ relations

![image](https://github.com/user-attachments/assets/0af2435e-3e37-4b7b-8454-d3944ed4a0a1)

--- 

# Phasors

##  Voltaje Phasor - Current Phasor

|**Time-domain representation**   | **Phasor-domain representation** |
|---------------------------------|----------------------------------|
| $V_m\cos(\omega t + \theta_v)$  | $V_m\angle \theta_v$             |
| $V_m\sin(\omega t + \theta_v)$  | $V_m\angle {\theta_v - 90°}$     |
| $I_m\cos(\omega t + \theta_i)$  | $I_m\angle \theta_i$             |
| $I_m\sin(\omega t + \theta_i)$  | $I_m\angle {\theta_i - 90°}$     |

---

# Instantaneous power

$p(t) = \frac{1}{2} V_m I_m \cos(\theta_v - \theta_i) + \frac{1}{2} V_m I_m \cos(2\omega t + \theta_v + \theta_i)$

# Average power

$p = \frac{1}{2} V_m I_m \cos(\theta_v - \theta_i)$

- **Case 1: Purely Resistive Load: $\theta_v = \theta_i$**

$p = \frac{1}{2}  V_m I_m$

- **Case 2: Purely Reactive Load: $\theta_v \not= \theta_i$**

$p= 0$

---

# Impedance triangle

![image](https://github.com/user-attachments/assets/8268f4f2-77b1-41ea-a95a-c184d0d62d9e)
