# AC and DC Analysis

**DC** circuits carry steady currents; **AC** circuits carry sinusoidally varying voltages and currents. AC analysis introduces phasors and impedance to turn differential equations into algebra.

## DC Transients

When a DC source is switched onto an RC or RL circuit, the response is exponential with a time constant:
\\[
\tau_{RC} = RC, \qquad \tau_{RL} = L/R, \qquad x(t) = x_\infty + (x_0 - x_\infty)e^{-t/\tau}.
\\]
After about \\(5\tau\\) the circuit reaches steady state.

## Phasors

A sinusoid \\(v(t) = V_m\cos(\omega t + \phi)\\) is represented by the complex **phasor** \\(\mathbf{V} = V_m\angle\phi\\). Derivatives become multiplication by \\(j\omega\\), so circuit equations become algebraic.

## Impedance

Each element has a complex impedance \\(Z = V/I\\):
\\[
Z_R = R, \qquad Z_L = j\omega L, \qquad Z_C = \frac{1}{j\omega C}.
\\]
Impedances combine in series/parallel exactly like resistances. The magnitude scales amplitude; the angle sets phase shift.

## Resonance

An RLC circuit resonates at
\\[
\omega_0 = \frac{1}{\sqrt{LC}},
\\]
where inductive and capacitive reactances cancel. The **quality factor** \\(Q = \omega_0 L/R\\) sets the sharpness of the resonance and the bandwidth \\(\Delta\omega = \omega_0/Q\\) — the basis of tuned filters and radios.

## AC Power

For sinusoidal steady state:
\\[
P = V_{\text{rms}} I_{\text{rms}}\cos\theta \ (\text{real, W}), \quad
Q = V_{\text{rms}} I_{\text{rms}}\sin\theta \ (\text{reactive, VAR}), \quad
S = V_{\text{rms}} I_{\text{rms}} \ (\text{apparent, VA}).
\\]
The **power factor** \\(\cos\theta\\) measures how much delivered power does real work; utilities penalize low power factor, corrected with capacitor banks. RMS of a sinusoid is \\(V_{\text{rms}} = V_m/\sqrt{2}\\).

## Three-Phase Power

Power systems use three phases 120° apart for constant instantaneous power and efficient transmission. Line and phase quantities relate by \\(\sqrt{3}\\) in wye/delta configurations.

## See Also

- [Circuit Laws](circuits.md)
- [Fourier Transform](../../signals/fourier-transform.md)
- [Laplace Transform](../../signals/laplace-transform.md)
