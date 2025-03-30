# AC circuits

![image](https://github.com/user-attachments/assets/b7ab8ffd-ad6f-415a-9d9a-d30c1bc14095)

## Voltages

$v(t)= v_m\sin(\omega t + \theta_v) [V]$

$v(t)= v_m\cos(\omega t + \theta_v) [V]$

## Currents

$i(t)= i_m\sin(\omega t + \theta_i) [A]$

$i(t)= i_m\cos(\omega t + \theta_i) [A]$

## Impedances

| Element          | Rectangular Form (\(Z\))       | Polar Form (\(Z\))                     | Angle (\(\theta\)) |
|------------------|--------------------------------|----------------------------------------|--------------------|
| **Resistor (R)** | \( R + j0 \)                   | \( R \angle 0^\circ \)                 | \( 0^\circ \)      |
| **Inductor (L)** | \( 0 + j\omega L \)            | \( \omega L \angle 90^\circ \)         | \( +90^\circ \)    |
| **Capacitor (C)**| \( 0 - j\frac{1}{\omega C} \)  | \( \frac{1}{\omega C} \angle -90^\circ \) | \( -90^\circ \) |
| **Series R+L**   | \( R + j\omega L \)            | \( \sqrt{R^2 + (\omega L)^2} \angle \tan^{-1}\left(\frac{\omega L}{R}\right) \) | \( \theta > 0 \) |
| **Series R+C**   | \( R - j\frac{1}{\omega C} \)  | \( \sqrt{R^2 + \left(\frac{1}{\omega C}\right)^2} \angle \tan^{-1}\left(\frac{-1}{\omega C R}\right) \) | \( \theta < 0 \) |
| **Parallel R\|L**| \( \frac{R \cdot j\omega L}{R + j\omega L} \) | \( \frac{R \omega L}{\sqrt{R^2 + (\omega L)^2}} \angle \tan^{-1}\left(\frac{R}{\omega L}\right) \) | \( 0^\circ < \theta < 90^\circ \) |
