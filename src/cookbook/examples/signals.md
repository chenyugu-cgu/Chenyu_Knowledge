# Signals and Systems Recipes

Runnable recipes for spectral analysis, filtering, and convolution.

---

## Recipe 1 — Compute and Read an FFT Spectrum

**Purpose.** Identify the frequency content of a sampled signal.

**Background.** The FFT computes the discrete Fourier transform in \\(O(N\log N)\\). The frequency resolution is \\(f_s/N\\) and the highest resolvable frequency is the Nyquist \\(f_s/2\\). See [Fourier Transform](../../signals/fourier-transform.md).

**Ingredients.** A sampled signal, the sampling rate \\(f_s\\).

**Method.**
1. Compute `rfft` of the signal.
2. Build the matching frequency axis with `rfftfreq`.
3. Find peaks in the magnitude spectrum.

**Example (Python).**
```python
import numpy as np

fs = 1000.0
t = np.arange(0, 1, 1/fs)
x = 2*np.sin(2*np.pi*50*t) + np.sin(2*np.pi*120*t)

X = np.abs(np.fft.rfft(x)) / len(t)
f = np.fft.rfftfreq(len(t), 1/fs)
peaks = f[np.argsort(X)[-2:]]
print("dominant frequencies:", np.sort(peaks))   # [50. 120.]
```

**Result.** Peaks at 50 Hz and 120 Hz, with the 50 Hz tone twice as tall.

**Variations.** Apply a window (Hann) before the FFT to reduce spectral leakage; use a spectrogram (STFT) for time-varying signals.

---

## Recipe 2 — Low-Pass Filter a Noisy Signal

**Purpose.** Remove high-frequency noise while preserving the signal.

**Background.** A Butterworth low-pass filter has a maximally flat passband. Zero-phase filtering (`filtfilt`) avoids phase distortion. See [Signal Processing](../../eng/electrical/signal-processing.md).

**Example (Python).**
```python
import numpy as np
from scipy import signal

fs = 500.0
t = np.arange(0, 2, 1/fs)
clean = np.sin(2*np.pi*3*t)
noisy = clean + 0.5*np.random.default_rng(0).normal(size=t.size)

b, a = signal.butter(4, 10/(fs/2), btype="low")   # cutoff 10 Hz
filtered = signal.filtfilt(b, a, noisy)
print("noise RMS before:", round((noisy-clean).std(), 3),
      "after:", round((filtered-clean).std(), 3))
```

**Result.** Residual noise drops markedly; the 3 Hz signal is preserved.

**Variations.** Use high-pass, band-pass, or notch filters; design FIR filters for exact linear phase.

---

## Recipe 3 — Estimate Delay by Cross-Correlation

**Purpose.** Find the time shift between two related signals.

**Background.** The lag maximizing cross-correlation is the delay — the basis of radar, sonar, and time-of-flight estimation. See [Convolution and Correlation](../../signals/convolution.md).

**Example (Python).**
```python
import numpy as np

rng = np.random.default_rng(0)
sig = rng.normal(size=500)
delay = 35
received = np.r_[np.zeros(delay), sig][:500] + 0.2*rng.normal(size=500)

corr = np.correlate(received, sig, mode="full")
est = corr.argmax() - (len(sig) - 1)
print("estimated delay:", est)     # ≈ 35
```

**Result.** Recovers a delay of ≈ 35 samples even with added noise.

**Variations.** Use the FFT-based correlation for long signals; interpolate the correlation peak for sub-sample resolution.

## References

- [Fourier Series](../../signals/fourier-series.md)
- [Sampling and Reconstruction](../../signals/sampling.md)
- [Convolution and Correlation](../../signals/convolution.md)
