# Energy Signals vs. Power Signals

# 1. Energy of a signal

**Definition=** Total energy is the integral (or sum) of the squared magnitude of the signal over all time. It quantifies the cumulative strength of the signal, where the 'strength' is the squared amplitude (energy is not linear in amplitude)

- **For continuous-time signals:**

  ## $E= \int_{-\infty}^{\infty} (\lvert x(t) \rvert)^{2} dt$

- **For discrete-time signals:**

  ## $E= \sum_{-\infty}^{\infty} (\lvert x[n] \rvert)^{2}$ 

**Energy Signal Condition**:  
A signal is classified as an **energy signal** if its total energy satisfies:
  # $$0 < E < \infty$$
*(Implies the signal must decay to zero as $t\rightarrow\infty$)*

**Key Properties**:
1. **Units**: Joules (J) for physical signals (e.g., voltage/current in 1Ω systems).
2. **Decay Requirement**: Finite energy implies $\lim_{|t| \to \infty} x(t) = 0$.
3. **Power Relationship**: Energy signals have:
   - Finite energy $( 0 < E < \infty )$
   - Zero average power $( P = 0 )$

