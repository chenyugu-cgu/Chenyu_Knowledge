# Convolution and Correlation

Convolution describes how an LTI system transforms an input via its impulse response; correlation measures the similarity between signals as a function of relative shift. They are computationally similar but conceptually distinct.

## Convolution

The continuous and discrete convolutions are
\\[
(x * h)(t) = \int_{-\infty}^{\infty} x(\tau)\,h(t-\tau)\,d\tau,
\qquad
(x * h)[n] = \sum_{k=-\infty}^{\infty} x[k]\,h[n-k].
\\]
Mechanically: **flip** \\(h\\), **shift** it by \\(t\\) (or \\(n\\)), **multiply** pointwise with \\(x\\), and **integrate/sum**.

### Properties

- **Commutative:** \\(x*h = h*x\\)
- **Associative:** \\((x*h)*g = x*(h*g)\\) — cascade systems multiply
- **Distributive:** \\(x*(h+g) = x*h + x*g\\) — parallel systems add
- **Identity:** \\(x*\delta = x\\)

### The Convolution Theorem

Convolution in time corresponds to multiplication in the transform domain:
\\[
x*h \;\leftrightarrow\; X(\omega)H(\omega)\ \text{(Fourier)},\quad X(s)H(s)\ \text{(Laplace)},\quad X(z)H(z)\ \text{(Z)}.
\\]
This is why FFT-based **fast convolution** (\\(O(N\log N)\\)) beats direct summation for long signals.

## Correlation

**Cross-correlation** measures similarity vs. lag \\(\tau\\):
\\[
R_{xy}(\tau) = \int_{-\infty}^{\infty} x^*(t)\,y(t+\tau)\,dt.
\\]
**Auto-correlation** \\(R_{xx}(\tau)\\) peaks at \\(\tau=0\\) and reveals periodicity. The only difference from convolution is that the second signal is **not** flipped:
\\[
R_{xy}(\tau) = x^*(-\tau) * y(\tau).
\\]

### Wiener–Khinchin Theorem

The power spectral density is the Fourier transform of the autocorrelation:
\\[
S_{xx}(\omega) = \int_{-\infty}^{\infty} R_{xx}(\tau)\,e^{-j\omega\tau}\,d\tau.
\\]

## Applications

- **Filtering:** output = input convolved with the filter's impulse response.
- **Matched filtering / radar / sonar:** correlate a received signal with a known template to detect it in noise and estimate delay.
- **Template matching** in image processing.
- **System identification:** estimate \\(h\\) from input–output cross-correlation.

## Example: Discrete Convolution and Lag Estimation

```python
import numpy as np

x = np.array([1, 2, 3])
h = np.array([0, 1, 0.5])
y = np.convolve(x, h)            # [0, 1, 2.5, 4, 1.5]
print("convolution:", y)

# Find the delay between a signal and a shifted, noisy copy
sig = np.random.randn(200)
delayed = np.r_[np.zeros(20), sig][:200] + 0.1*np.random.randn(200)
corr = np.correlate(delayed, sig, mode="full")
lag = corr.argmax() - (len(sig) - 1)
print("estimated lag:", lag)     # ~20
```

## See Also

- [Time-Domain Analysis](time-domain.md)
- [Fourier Transform](fourier-transform.md)
