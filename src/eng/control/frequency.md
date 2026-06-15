# Frequency Response

The **frequency response** \\(G(j\omega)\\) describes how a system responds to sinusoids of every frequency. It is obtained by evaluating the transfer function on the imaginary axis, \\(s = j\omega\\), and is the foundation of classical loop-shaping design.

## Magnitude and Phase

For sinusoidal input at frequency \\(\omega\\), the steady-state output is a sinusoid of the same frequency, scaled by \\(|G(j\omega)|\\) and shifted by \\(\angle G(j\omega)\\):
\\[
|G(j\omega)| = \text{gain}, \qquad \angle G(j\omega) = \text{phase shift}.
\\]

## Bode Plots

A **Bode plot** shows magnitude in decibels (\\(20\log_{10}|G|\\)) and phase in degrees, both vs. \\(\log\omega\\). Its power is that cascaded systems **add** on a Bode plot. Asymptotic rules:

- A pole contributes \\(-20\\) dB/decade and \\(-90^\circ\\); a zero contributes \\(+20\\) dB/decade and \\(+90^\circ\\).
- The break occurs at the corner frequency \\(\omega = |p|\\) or \\(|z|\\).

This makes hand-sketching and loop-shaping intuitive.

## Bandwidth and Resonance

- **Bandwidth** \\(\omega_B\\): frequency where gain drops 3 dB below DC — a measure of response speed.
- **Resonant peak** \\(M_r\\): the maximum of \\(|G(j\omega)|\\); large peaks indicate low damping and ringing.

## Nyquist and Nichols

The **Nyquist plot** is the polar plot of \\(G(j\omega)\\) used for the stability criterion (see [Stability Analysis](stability.md)). The **Nichols chart** plots gain vs. phase and directly shows closed-loop response and margins.

## Loop Shaping

Design by shaping the open-loop \\(L(j\omega) = C(j\omega)G(j\omega)\\):

- **High gain at low frequency** → good tracking and disturbance rejection.
- **Low gain at high frequency** → noise attenuation and robustness.
- **Adequate phase margin near crossover** → stability and damping.

Lead compensators add phase (improve stability), lag compensators add low-frequency gain (improve accuracy).

## Worked Example

For \\(G(s) = \dfrac{1}{s(s+1)}\\), the magnitude crosses 0 dB near \\(\omega \approx 0.79\\) rad/s with phase \\(\approx -128^\circ\\), giving a phase margin of about \\(52^\circ\\) — a stable, reasonably damped loop.

## See Also

- [Fourier Transform](../../signals/fourier-transform.md)
- [Stability Analysis](stability.md)
- [PID Control](pid.md)
