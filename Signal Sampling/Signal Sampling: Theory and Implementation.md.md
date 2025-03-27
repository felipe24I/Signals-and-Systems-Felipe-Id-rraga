# Signal Sampling: Theory and Implementation

![image](https://github.com/user-attachments/assets/ceb1e903-8654-46f8-af4c-405f4d03ad73)

**Definition:** Process that discretice a signal $x(t)$ for capture samplings for each $T_s$ 

**$F_s$:** How many samplings occurs in one second

**$T_s$:** How many time transcurs bewteen each sampling

**$t_n$:** Discrete time

**$t_n$:** $n*T_s$

**Note:** Samplings are always integers

# **A sample and hold circuit**

![image](https://github.com/user-attachments/assets/6388e3ad-dd69-4907-acb4-287dedf0b6b2)

**CK**: Clock signal, provides acontrol signal for sampling

**Capacitor**: 
  - **When switch ON**: Capacitor charges the voltage from input signal
  - **When switch OFF**: Capacitor retern this voltage for ADC converter process this value

    
