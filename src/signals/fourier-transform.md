# Fourier Transform

The Fourier transform generalizes the Fourier series to **aperiodic** signals by letting the period grow without bound. It maps a time-domain signal into a continuous spectrum of frequencies and is the single most important tool in signal processing, communications, optics, and quantum mechanics.

## Definition

The continuous-time Fourier transform (CTFT) and its inverse are
\\[
X(\omega) = \int_{-\infty}^{\infty} x(t)\,e^{-j\omega t}\, dt,
\qquad
x(t) = \frac{1}{2\pi}\int_{-\infty}^{\infty} X(\omega)\,e^{j\omega t}\, d\omega.
\\]
\\(X(\omega)\\) is generally complex: \\(|X(\omega)|\\) is the **magnitude spectrum** and \\(\arg X(\omega)\\) the **phase spectrum**.

## Key Properties

| Property | Time domain | Frequency domain |
|---|---|---|
| Linearity | \\(a x_1 + b x_2\\) | \\(a X_1 + b X_2\\) |
| Time shift | \\(x(t-t_0)\\) | \\(e^{-j\omega t_0}X(\omega)\\) |
| Frequency shift | \\(e^{j\omega_0 t}x(t)\\) | \\(X(\omega-\omega_0)\\) |
| Scaling | \\(x(at)\\) | \\(\frac{1}{|a|}X(\omega/a)\\) |
| Differentiation | \\(\frac{d}{dt}x(t)\\) | \\(j\omega X(\omega)\\) |
| **Convolution** | \\(x*h\\) | \\(X(\omega)H(\omega)\\) |
| Multiplication | \\(x(t)w(t)\\) | \\(\frac{1}{2\pi}X*W\\) |

The **convolution theorem** — convolution in time is multiplication in frequency — is the reason the frequency domain is so powerful: it turns the messy convolution integral into a simple product.

## Common Transform Pairs

\\[
\delta(t) \leftrightarrow 1, \qquad
1 \leftrightarrow 2\pi\,\delta(\omega), \qquad
e^{-at}u(t) \leftrightarrow \frac{1}{a + j\omega}\ (a>0),
\\]
\\[
\operatorname{rect}(t/T) \leftrightarrow T\,\operatorname{sinc}\!\left(\frac{\omega T}{2\pi}\right),
\qquad
\cos(\omega_0 t) \leftrightarrow \pi[\delta(\omega-\omega_0)+\delta(\omega+\omega_0)].
\\]

## Parseval / Rayleigh Energy Theorem

\\[
\int_{-\infty}^{\infty}|x(t)|^2\,dt = \frac{1}{2\pi}\int_{-\infty}^{\infty}|X(\omega)|^2\,d\omega.
\\]
Energy is conserved between domains; \\(|X(\omega)|^2\\) is the **energy spectral density**.

## Discrete and Fast Fourier Transforms

For sampled data of length \\(N\\), the **Discrete Fourier Transform (DFT)** is
\\[
X[k] = \sum_{n=0}^{N-1} x[n]\,e^{-j 2\pi k n / N}, \qquad k = 0,\dots,N-1.
\\]
The **Fast Fourier Transform (FFT)** computes the DFT in \\(O(N\log N)\\) instead of \\(O(N^2)\\) and is the workhorse of practical spectral analysis.

```python
import numpy as np

fs = 1000.0                      # sampling rate [Hz]
t = np.arange(0, 1, 1/fs)
x = np.sin(2*np.pi*50*t) + 0.5*np.sin(2*np.pi*120*t)

X = np.fft.rfft(x)               # real FFT
f = np.fft.rfftfreq(len(x), 1/fs)
peaks = f[np.argsort(np.abs(X))[-2:]]
print("Dominant frequencies (Hz):", np.sort(peaks))   # ~50 and 120
```

## See Also

- [Fourier Series](fourier-series.md)
- [Sampling and Reconstruction](sampling.md)
- [Convolution and Correlation](convolution.md)
