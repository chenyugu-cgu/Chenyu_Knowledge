# The Wave Equation

The wave equation is the master equation of all wave phenomena, derived from a restoring force proportional to curvature plus inertia.

## The Equation and Its Solutions

\\[
\frac{\partial^2 u}{\partial t^2} = c^2\frac{\partial^2 u}{\partial x^2}.
\\]
**d'Alembert's solution** shows any wave is a superposition of left- and right-traveling shapes:
\\[
u(x,t) = f(x - ct) + g(x + ct).
\\]
\\(c\\) is the wave speed — e.g. \\(c = \sqrt{T/\mu}\\) for a string, \\(\sqrt{B/\rho}\\) for sound.

## Harmonic Waves

A sinusoidal wave \\(u = A\cos(kx - \omega t)\\) has wavenumber \\(k = 2\pi/\lambda\\), angular frequency \\(\omega\\), and the **dispersion relation** \\(\omega = ck\\). Speeds: phase \\(v_p = \omega/k\\) and group \\(v_g = d\omega/dk\\) (energy/information speed); they differ in dispersive media.

## Standing Waves and Modes

On a bounded domain, boundary conditions quantize the allowed wavelengths into **modes** (harmonics):
\\[
f_n = \frac{n c}{2L}, \quad n = 1, 2, \dots
\\]
This is why instruments have discrete pitches and why structures and cavities have natural frequencies — solved by [separation of variables](../../math/diffeq/pdes.md).

## Superposition and Interference

Because the equation is linear, waves add. Overlapping waves interfere constructively or destructively — the basis of [wave optics](wave-optics.md), beats, and noise cancellation.

## Energy

A wave's energy density is proportional to amplitude squared; intensity (power per area) falls as \\(1/r^2\\) for spherical spreading.

## See Also

- [Acoustics](acoustics.md)
- [Partial Differential Equations](../../math/diffeq/pdes.md)
- [Fourier Series](../../signals/fourier-series.md)
