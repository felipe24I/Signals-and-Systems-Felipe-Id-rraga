# Exponential Signal

The exponential signal is a fundamental signal in signal processing and system analysis.

## Definition

The exponential signal is defined as:

$$x(t) = e^{at}$$

Where:
- $a$ is a real constant that determines the behavior of the signal
- $t$ represents time

## Behavior

The signal behavior depends on the value of parameter $a$:

- **Decreasing**: When $a < 0$, the signal decreases exponentially over time
- **Increasing**: When $a > 0$, the signal increases exponentially over time

## Visual Representation

The exponential signal has two characteristic shapes:

### Increasing exponential ($a > 0$)

![Increasing Exponential Signal](./images/increasing_exponential.png)

- Starts at 1 when $t = 0$
- Grows progressively faster as time increases
- Follows a convex curve upward

### Decreasing exponential ($a < 0$)

![Decreasing Exponential Signal](./images/decreasing_exponential.png)

- Starts at 1 when $t = 0$
- Decreases rapidly at first, then approaches zero asymptotically
- Follows a concave curve approaching the time axis

## Applications

The primary utility of exponential signals is modeling natural growth and decay processes, such as:

- Population growth
- Radioactive decay
- Charging/discharging of capacitors
- Temperature changes in thermal systems
- Chemical reactions
- Economic growth or depreciation
- Biological processes

## Properties

- Value at $t = 0$ is always 1 (regardless of $a$)
- When $a = 0$, the signal becomes constant: $x(t) = e^0 = 1$
- The exponential signal is the eigenfunction of linear time-invariant systems
