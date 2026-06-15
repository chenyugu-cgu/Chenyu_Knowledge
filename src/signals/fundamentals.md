# Fundamentals of Signals

A **signal** is a function that conveys information about the behavior of a physical system or phenomenon. Mathematically, a signal is a map from an independent variable (usually time or space) to a dependent quantity (voltage, pressure, displacement, intensity). A **system** is an operator that transforms an input signal into an output signal. The study of signals and systems gives us a unified language for everything from audio processing to control loops to medical imaging.

## Classification of Signals

### Continuous-Time vs. Discrete-Time

- **Continuous-time** signals \\(x(t)\\) are defined for every real \\(t \in \mathbb{R}\\).
- **Discrete-time** signals \\(x[n]\\) are defined only at integer indices \\(n \in \mathbb{Z}\\), typically obtained by sampling: \\(x[n] = x(nT_s)\\), where \\(T_s\\) is the sampling period.

### Analog vs. Digital

A signal is **analog** if both its independent and dependent variables are continuous, and **digital** if both are quantized (discrete in time and amplitude). Digitization involves *sampling* (time) and *quantization* (amplitude).

### Deterministic vs. Random

A **deterministic** signal can be described by an explicit mathematical rule. A **random** (stochastic) signal can only be characterized statistically (mean, variance, power spectral density).

### Periodic vs. Aperiodic

A continuous signal is **periodic** with period \\(T\\) if \\(x(t) = x(t + T)\\) for all \\(t\\); the smallest such \\(T\\) is the fundamental period. For discrete signals, \\(x[n] = x[n+N]\\) with integer \\(N\\).

### Energy vs. Power Signals

The **energy** and **average power** of a signal are
\\[
E = \int_{-\infty}^{\infty} |x(t)|^2\, dt, \qquad
P = \lim_{T \to \infty} \frac{1}{2T}\int_{-T}^{T} |x(t)|^2\, dt.
\\]
A signal is an **energy signal** if \\(0 < E < \infty\\) (then \\(P = 0\\)), and a **power signal** if \\(0 < P < \infty\\) (then \\(E = \infty\\)). Periodic signals are power signals; finite-duration pulses are energy signals.

## Elementary Signals

| Signal | Continuous form | Discrete form |
|---|---|---|
| Unit impulse | \\(\delta(t)\\) | \\(\delta[n]\\) |
| Unit step | \\(u(t)\\) | \\(u[n]\\) |
| Ramp | \\(r(t) = t\,u(t)\\) | \\(r[n] = n\,u[n]\\) |
| Exponential | \\(e^{st}\\) | \\(z^{n}\\) |
| Sinusoid | \\(A\cos(\omega t + \phi)\\) | \\(A\cos(\Omega n + \phi)\\) |

The **Dirac delta** is defined by its sifting property:
\\[
\int_{-\infty}^{\infty} x(t)\,\delta(t - t_0)\, dt = x(t_0),
\\]
while the discrete **Kronecker delta** is \\(\delta[n] = 1\\) for \\(n=0\\) and \\(0\\) otherwise. The unit step is the running integral (sum) of the impulse: \\(u(t) = \int_{-\infty}^{t}\delta(\tau)\,d\tau\\).

## Signal Operations

- **Time shift:** \\(x(t - t_0)\\) delays the signal by \\(t_0\\).
- **Time scaling:** \\(x(at)\\) compresses (\\(|a|>1\\)) or stretches (\\(|a|<1\\)) the signal.
- **Time reversal:** \\(x(-t)\\) reflects about \\(t=0\\).
- **Amplitude scaling and bias:** \\(c\,x(t) + d\\).

Any signal can be decomposed into **even** and **odd** parts:
\\[
x_e(t) = \tfrac{1}{2}\big(x(t) + x(-t)\big), \qquad
x_o(t) = \tfrac{1}{2}\big(x(t) - x(-t)\big).
\\]

## Why This Matters

Every later chapter — Fourier and Laplace analysis, sampling, convolution, stability — builds on these definitions. Choosing the right representation (time vs. frequency, continuous vs. discrete, energy vs. power) is half the battle in any practical signal-processing or control problem.

## See Also

- [Time-Domain Analysis](time-domain.md)
- [Sampling and Reconstruction](sampling.md)
- [Convolution and Correlation](convolution.md)
