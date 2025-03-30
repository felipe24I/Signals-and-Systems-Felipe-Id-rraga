# Energy Signals vs. Power Signals

# 1. Energy of a Signal

**Definition**:  
Total energy is the integral (or sum) of the squared magnitude of the signal over all time. It quantifies the cumulative strength of the signal, where the 'strength' is the squared amplitude (energy is not linear in amplitude).

### Continuous-time:
$$E=\int_{-\infty}^{\infty}|x(t)|^2dt$$

### Discrete-time:
$$E=\sum_{n=-\infty}^{\infty}|x[n]|^2$$

**Energy Signal Condition**:  
A signal is an **energy signal** if:
1. Total energy satisfies: $$0<E<\infty$$
2. Implies: $$\lim_{t\to\infty}x(t)=0$$

**Key Properties**:
1. **Units**: Joules (J)
2. **Decay**: Must satisfy $$\lim_{|t|\to\infty}x(t)=0$$
3. **Power**: 
   - Finite energy: $$0<E<\infty$$
   - Zero average power: $$P=0$$

# 2. Power of a Signal

**Definition**:  
Power measures the average energy per unit time, representing sustained signal strength.

### Continuous-time:
$$P=\lim_{T\to\infty}\frac{1}{T}\int_{-T/2}^{T/2}|x(t)|^2dt$$

### Discrete-time:
$$P=\lim_{N\to\infty}\frac{1}{2N+1}\sum_{n=-N}^{N}|x[n]|^2$$

**Power Signal Condition**:  
A signal is a **power signal** if:
1. Total energy is infinite: $$E=\infty$$
2. Average power is finite: $$0<P<\infty$$

**Key Properties**:
1. **Units**: Watts (W)
2. **Behavior**: Does not decay (persists indefinitely)
3. **Examples**:
   - Periodic signals (sine waves)
   - Constant signals
   - Stationary noise processes
4. **Analysis**: Requires power spectral density (PSD)
