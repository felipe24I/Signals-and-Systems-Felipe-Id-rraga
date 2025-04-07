# **SYSTEMS AND CLASSIFICATION OF SYSTEMS**

## **A. System Representation**

mathematical model of a physical process that relates the input (or excitation) signal to the output (or response) signal

- x = Input signal
- y = Output signal

System is viewed as a **transformation** of **$x$** into **$y$**

$y = Tx$

![image](https://github.com/user-attachments/assets/ab6b480e-62f5-4ee9-89f9-38fa2212f2f4)


![image](https://github.com/user-attachments/assets/c440fe07-3403-4551-b52f-8fd2f5cf813b)


## **B. Continuous-Time  and Discrete-Time Systems**

**Continuous-Time System:** If the input and output signals are continuous-time signals

![image](https://github.com/user-attachments/assets/b993f212-42de-4fba-991e-e91577cbaaac)


**Discrete-Time System:** If the input and output signals are continuous-time signals or sequences

![image](https://github.com/user-attachments/assets/d9d05608-4548-41ef-92bc-21c73b0a8d41)


## **C. Systems with Memory and without Memory**

**Systems without Memory:** If the output at any time depends of only the input at that same time

- Resistor R with $x(t)$=  Current, $y(t)$= voltage, and $y(t) = Rx(t)$

**Systems with Memory:** If the output at any time depends of the input at any  time

- Capacitor C with $x(t)$=  Current, $y(t)$= voltage, and $y(t) = \frac{1}{C}\int_{-∞}^t x(τ)dτ$

- Discrete-time system, $y[n]= \sum_{k= -∞}^n x[k]$

## **D. Causal and Noncausal Systems:**

- **Causal:** If it's output at an arbitrary time $t=t_0$ depends on only the input $x(t)$ for $t \leq t_0$

- **Noncausal:** if is not causal

**Examples of noncausal systems**

- $y(t)= x(t + 1)$

- $y[n] = x[-n]$

Note that all memoryless systems are causal, but not  vice versa

## **E. Linear Systems and Nonlinear Systems:**

- **Linear system:** A system represented by a linear operator T, it must satisfies the two following conditions

1. **Additivity:**

Given that $Tx_1 = y_1$ and $Tx_2 = y_2$, then:

$T[x_1 + x_2] = y_1 + y_2$

for any signals $x_1$ and $x_2$

2. **Homogeneity (or scaling):**

$T[αx] = αy$

previous conditions can be combined into a signle condition called **superposition property**

$T[\alpha_1 x_1 + \alpha_2 x_2]= \alpha_1 y_1 + \alpha_2 y_2$

Examples of linear systems:

- Resistor equation

- Capacitor equation

**Nonlinear system: Any system that does not satisfy the previous two conditions** 

Examples of Nonlinear systems:

- $y= x^2$

- $y= cos(x)$

## F. **Time-Invariant and Time-Varying Systems:**

**Time-Invariant system:** If a time shift (delay or advance) in the input signal causes the same time shift in the output signal

- $T[x(t - \tau)] = y(t-\tau)$ for any real value of $\tau$

- $T[x(n - k)] = y(n- k)$ for any integer $k$


**Time-varying system:** A system which not satisfy previous equations

**Note:** To check a system for time-invariance, we can compare the shifted output with the output produced by the shifted input

## G. **Linear Time-Invariant Systems:**

**(LTI) System:** If the system is linear and also time-invariant 

## H. **Stable Systmes:** 

A system is bounded-input /bounded output (BIBO) **stable** if for any bounded input $x$ defined by

$\mid x \mid ≤ k_1$

the corresponding output $y$ is also bounded defined by 

$\mid y \mid ≤ k_2$

where $k_1$ and $k_2$ are finite real constants

## I. **Feedback systems:**

The output signal is fed back and added to the input to the system

![image](https://github.com/user-attachments/assets/0f2a91ca-b402-430e-a353-9d32259d2943)

