# Vibrations

Vibration is oscillatory motion about an equilibrium. It governs everything from bridge resonance to vehicle suspension to MEMS sensors. The single most important model is the **mass–spring–damper**.

## Free Undamped Vibration

A mass \\(m\\) on a spring \\(k\\) obeys
\\[
m\ddot{x} + k x = 0 \ \Rightarrow\ \ddot{x} + \omega_n^2 x = 0,
\qquad \omega_n = \sqrt{\frac{k}{m}}.
\\]
The motion is simple harmonic, \\(x(t) = A\cos(\omega_n t + \phi)\\), at the **natural frequency** \\(\omega_n\\) (rad/s), \\(f_n = \omega_n/2\pi\\) (Hz).

## Free Damped Vibration

Adding viscous damping \\(c\\):
\\[
m\ddot{x} + c\dot{x} + k x = 0 \ \Rightarrow\ \ddot{x} + 2\zeta\omega_n \dot{x} + \omega_n^2 x = 0,
\\]
where the **damping ratio** is \\(\zeta = c/(2\sqrt{km})\\). Behavior depends on \\(\zeta\\):

| Regime | \\(\zeta\\) | Response |
|---|---|---|
| Underdamped | \\(0<\zeta<1\\) | decaying oscillation at \\(\omega_d = \omega_n\sqrt{1-\zeta^2}\\) |
| Critically damped | \\(\zeta=1\\) | fastest return without overshoot |
| Overdamped | \\(\zeta>1\\) | slow, non-oscillatory return |

The **logarithmic decrement** \\(\delta = \ln(x_i/x_{i+1}) = 2\pi\zeta/\sqrt{1-\zeta^2}\\) lets you measure \\(\zeta\\) from a decay record.

## Forced Vibration and Resonance

Under harmonic forcing \\(F_0\cos\omega t\\), the steady-state amplitude is
\\[
X(\omega) = \frac{F_0/k}{\sqrt{(1-r^2)^2 + (2\zeta r)^2}}, \qquad r = \frac{\omega}{\omega_n}.
\\]
The dynamic magnification peaks near \\(r=1\\) — **resonance**. Light damping gives huge amplification (the Tacoma Narrows lesson); this is why machines are run away from their natural frequencies.

## Vibration Isolation

The **transmissibility** (fraction of force/motion transmitted through a mount) is
\\[
TR = \sqrt{\frac{1 + (2\zeta r)^2}{(1-r^2)^2 + (2\zeta r)^2}}.
\\]
Isolation (\\(TR<1\\)) requires \\(r > \sqrt{2}\\): the mount must be **soft** relative to the disturbance frequency.

## Multi-Degree-of-Freedom Systems

Systems with several masses are written \\(\mathbf{M}\ddot{\mathbf{x}} + \mathbf{K}\mathbf{x} = \mathbf{0}\\); the eigenvalues of \\(\mathbf{M}^{-1}\mathbf{K}\\) give the squared natural frequencies and the eigenvectors give the **mode shapes**. See [Eigenvalues and Eigenvectors](../../math/linear-algebra/eigen.md).

## See Also

- [Work and Energy](energy.md)
- [Fundamentals of Signals](../../signals/fundamentals.md)
- [Modeling of Systems](../control/modeling.md)
