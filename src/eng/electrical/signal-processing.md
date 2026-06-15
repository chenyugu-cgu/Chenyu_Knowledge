# Signal Processing

Digital signal processing (DSP) acquires, transforms, and analyzes signals with numerical algorithms. It is where [signals theory](../../signals/fundamentals.md) meets electronics and computing.

## The DSP Chain

\\[
\text{analog} \xrightarrow{\text{anti-alias filter}} \text{ADC} \xrightarrow{} \text{digital processing} \xrightarrow{} \text{DAC} \xrightarrow{\text{reconstruction filter}} \text{analog}.
\\]
The **anti-aliasing filter** removes energy above the Nyquist frequency before sampling; see [Sampling and Reconstruction](../../signals/sampling.md).

## Digital Filters

A digital filter computes outputs from inputs via a difference equation:
\\[
y[n] = \sum_{m=0}^{M} b_m x[n-m] - \sum_{k=1}^{N} a_k y[n-k].
\\]

- **FIR** (\\(a_k = 0\\)): always stable, can be exactly linear-phase, designed by windowing or Parks–McClellan.
- **IIR**: uses feedback, efficient (fewer taps), designed from analog prototypes (Butterworth, Chebyshev, elliptic) via the bilinear transform.

## Frequency Analysis

The **FFT** computes the spectrum in \\(O(N\log N)\\). Practical spectral analysis uses **windowing** (Hann, Hamming) to reduce leakage and **overlap-add/save** for filtering long signals. The **spectrogram** (short-time FFT) reveals how spectra evolve in time.

```python
import numpy as np
from scipy import signal

fs = 1000.0
t = np.arange(0, 1, 1/fs)
x = np.sin(2*np.pi*5*t) + np.sin(2*np.pi*150*t)   # 5 Hz signal + 150 Hz noise

# Low-pass Butterworth at 30 Hz removes the high-frequency component
b, a = signal.butter(4, 30/(fs/2), btype="low")
y = signal.filtfilt(b, a, x)                      # zero-phase filtering
print("input std:", round(x.std(), 3), " filtered std:", round(y.std(), 3))
```

## Applications

- **Audio:** equalization, compression, noise reduction, effects.
- **Communications:** modulation/demodulation, channel equalization, error coding.
- **Imaging and radar:** 2-D filtering, beamforming, pulse compression.
- **Biomedical:** ECG/EEG filtering and feature extraction — see [Medical Imaging](../../app/biomed/imaging.md).

## See Also

- [Fourier Transform](../../signals/fourier-transform.md)
- [Sampling and Reconstruction](../../signals/sampling.md)
- [Signals and Systems Recipes](../../cookbook/examples/signals.md)
