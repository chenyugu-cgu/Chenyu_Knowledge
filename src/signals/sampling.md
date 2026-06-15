# Sampling and Reconstruction

Sampling converts a continuous-time signal into a discrete sequence so it can be processed digitally. Reconstruction recovers a continuous signal from its samples. The central question is: *when does sampling lose no information?* The answer is the Nyquist–Shannon sampling theorem.

## Ideal Sampling

Ideal sampling multiplies \\(x(t)\\) by an impulse train \\(p(t)=\sum_n \delta(t - nT_s)\\) with sampling period \\(T_s\\) and sampling rate \\(f_s = 1/T_s\\). In the frequency domain this **periodically replicates** the spectrum:
\\[
X_s(\omega) = \frac{1}{T_s}\sum_{k=-\infty}^{\infty} X(\omega - k\omega_s), \qquad \omega_s = 2\pi f_s.
\\]

## The Sampling Theorem

A bandlimited signal with maximum frequency \\(f_{\max}\\) (no energy above \\(f_{\max}\\)) is **completely determined** by samples taken at rate
\\[
f_s > 2 f_{\max}.
\\]
The threshold \\(2 f_{\max}\\) is the **Nyquist rate**; \\(f_s/2\\) is the **Nyquist frequency**.

## Aliasing

If \\(f_s < 2 f_{\max}\\), spectral replicas overlap and high frequencies masquerade as lower ones — **aliasing**. A component at \\(f\\) appears at the alias frequency
\\[
f_{\text{alias}} = |f - k f_s|\quad\text{for the integer } k \text{ minimizing it.}
\\]
The cure is an **anti-aliasing low-pass filter** applied *before* sampling to remove energy above \\(f_s/2\\).

## Reconstruction (Interpolation)

Ideal reconstruction passes the samples through a low-pass filter with cutoff \\(f_s/2\\), which in the time domain is **sinc interpolation**:
\\[
x(t) = \sum_{n=-\infty}^{\infty} x[n]\,\operatorname{sinc}\!\left(\frac{t - nT_s}{T_s}\right),
\qquad \operatorname{sinc}(u)=\frac{\sin(\pi u)}{\pi u}.
\\]
Practical converters use **zero-order hold** (staircase) followed by a smoothing filter, which approximates the ideal sinc.

## Quantization

Real ADCs also quantize amplitude to \\(B\\) bits. Uniform quantization with step \\(\Delta\\) introduces noise of power \\(\Delta^2/12\\), giving the classic signal-to-quantization-noise ratio
\\[
\text{SQNR} \approx 6.02\,B + 1.76\ \text{dB}.
\\]
Every extra bit buys about 6 dB.

## Example: Demonstrating Aliasing

```python
import numpy as np
fs = 100.0                       # sampling rate
n = np.arange(0, 1, 1/fs)
# A 90 Hz tone sampled at 100 Hz aliases to |90 - 100| = 10 Hz
x = np.sin(2*np.pi*90*n)
spectrum = np.abs(np.fft.rfft(x))
freqs = np.fft.rfftfreq(len(n), 1/fs)
print("Apparent peak:", round(freqs[np.argmax(spectrum)], 1), "Hz")  # ~10 Hz
```

## See Also

- [Fourier Transform](fourier-transform.md)
- [Z-Transform](z-transform.md)
- [Signal Processing](../eng/electrical/signal-processing.md)
