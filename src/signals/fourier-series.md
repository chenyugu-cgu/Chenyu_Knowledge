# Fourier Series

The Fourier series expresses any reasonable **periodic** signal as a sum of harmonically related sinusoids (or complex exponentials). It is the gateway to frequency-domain thinking: instead of asking "what is the signal at each instant?" we ask "how much of each frequency does the signal contain?"

## Complex Exponential Form

For a signal periodic with period \\(T\\) and fundamental frequency \\(\omega_0 = 2\pi/T\\),
\\[
x(t) = \sum_{k=-\infty}^{\infty} c_k\, e^{j k \omega_0 t},
\qquad
c_k = \frac{1}{T}\int_{T} x(t)\, e^{-j k \omega_0 t}\, dt.
\\]
The complex coefficients \\(c_k\\) are the **spectrum** of the signal: \\(|c_k|\\) gives the amplitude and \\(\arg c_k\\) the phase of the \\(k\\)-th harmonic.

## Trigonometric Form

Equivalently,
\\[
x(t) = a_0 + \sum_{k=1}^{\infty}\big(a_k\cos k\omega_0 t + b_k \sin k\omega_0 t\big),
\\]
with
\\[
a_0 = \frac{1}{T}\int_T x(t)\,dt,\quad
a_k = \frac{2}{T}\int_T x(t)\cos k\omega_0 t\,dt,\quad
b_k = \frac{2}{T}\int_T x(t)\sin k\omega_0 t\,dt.
\\]
The relations \\(c_0 = a_0\\) and \\(c_k = \tfrac{1}{2}(a_k - j b_k)\\) connect the two forms.

## Dirichlet Conditions

A periodic signal has a convergent Fourier series if, over one period, it is absolutely integrable, has a finite number of maxima/minima, and a finite number of finite discontinuities. At a jump, the series converges to the **midpoint** of the discontinuity.

## Parseval's Theorem (Power)

The average power of a periodic signal equals the sum of the powers of its harmonics:
\\[
\frac{1}{T}\int_T |x(t)|^2\, dt = \sum_{k=-\infty}^{\infty} |c_k|^2.
\\]

## Gibbs Phenomenon

Truncating the series near a discontinuity produces a persistent overshoot of about **9%** of the jump that does not vanish as more terms are added — it merely narrows. This matters when synthesizing square waves or sharp edges with finite bandwidth.

## Example: Square Wave

For an odd square wave of amplitude \\(A\\) and period \\(T\\), only odd harmonics survive:
\\[
x(t) = \frac{4A}{\pi}\sum_{k=1,3,5,\dots} \frac{1}{k}\sin(k\omega_0 t).
\\]
The amplitudes decay as \\(1/k\\), which is why square waves are rich in high-frequency content.

```python
import numpy as np
import matplotlib.pyplot as plt

t = np.linspace(0, 2, 2000)
w0 = 2 * np.pi          # fundamental (period = 1 s)
A = 1.0
x = np.zeros_like(t)
for k in range(1, 100, 2):      # odd harmonics only
    x += (4 * A / np.pi) * np.sin(k * w0 * t) / k

plt.plot(t, x)
plt.title("Square wave from 50 odd harmonics (note Gibbs overshoot)")
plt.xlabel("t [s]"); plt.ylabel("x(t)")
plt.show()
```

## See Also

- [Fourier Transform](fourier-transform.md) — the limit as the period \\(T \to \infty\\).
- [Applications in Engineering](applications.md)
