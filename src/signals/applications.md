# Applications in Engineering

The abstract machinery of signals and systems pays off across nearly every engineering discipline. This chapter surveys where each tool earns its keep.

## Communications

- **Modulation** shifts a baseband signal to a carrier frequency: AM multiplies \\(x(t)\cos\omega_c t\\); FM/PM encode information in phase. The Fourier transform's frequency-shift property explains the resulting spectra.
- **Matched filtering** maximizes signal-to-noise ratio for detection by correlating against a known pulse shape.
- **Channel equalization** inverts a distorting channel \\(H(\omega)\\) with an equalizer \\(1/H(\omega)\\).

## Audio and Speech

- **Filtering** (EQ, bass/treble) is convolution with a designed impulse response.
- **Spectrograms** apply the short-time Fourier transform to show how frequency content evolves.
- **Compression** (MP3, AAC) discards perceptually irrelevant frequency components revealed by the FFT.

## Image and Video Processing

- 2-D convolution implements blurring, sharpening, and edge detection (Sobel, Laplacian kernels).
- The 2-D DFT/DCT underlies JPEG compression and frequency-domain denoising.

## Biomedical Signals

- **ECG/EEG/EMG** analysis relies on band-pass filtering, notch filters (50/60 Hz removal), and spectral analysis to extract physiological rhythms.
- **Medical imaging** (MRI, CT) literally reconstructs images from frequency-domain or projection data — MRI samples k-space, CT inverts the Radon transform. See [Medical Imaging](../app/biomed/imaging.md).

## Control Systems

- Transfer functions, Bode plots, and stability margins come straight from Laplace/Fourier analysis. See [Frequency Response](../eng/control/frequency.md).
- Sampling theory governs the design of digital controllers and anti-aliasing filters.

## Vibration and Structural Health

- Modal analysis identifies natural frequencies from the FFT of accelerometer data.
- Order tracking and envelope analysis detect bearing and gear faults in rotating machinery. See [Vibrations](../eng/dynamics/vibrations.md).

## A Unifying View

| Tool | Best for |
|---|---|
| Fourier series | steady-state response to periodic inputs |
| Fourier transform | spectral content of aperiodic / finite-energy signals |
| Laplace transform | transients, initial conditions, control design |
| Z-transform | digital filters, sampled-data systems |
| Convolution | filtering, system response |
| Correlation | detection, delay/feature estimation |

Mastering when to reach for each transform is the practical payoff of this whole section.

## See Also

- [Signal Processing](../eng/electrical/signal-processing.md)
- [Signals and Systems Recipes](../cookbook/examples/signals.md)
