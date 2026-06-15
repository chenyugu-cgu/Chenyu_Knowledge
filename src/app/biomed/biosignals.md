# Biosignal Processing

Biosignals are the electrical, mechanical, and chemical signals the body produces — ECG, EEG, EMG, and more. Processing them to extract clinically useful information is a core biomedical engineering skill, applying [signal processing](../../eng/electrical/signal-processing.md) to physiology.

## Major Biosignals

| Signal | Source | Typical band |
|---|---|---|
| **ECG** | heart electrical activity | 0.05–150 Hz |
| **EEG** | brain electrical activity | 0.5–50 Hz |
| **EMG** | muscle activation | 20–500 Hz |
| **PPG** | blood volume (optical) | <10 Hz |
| **Respiration** | breathing | <1 Hz |

These are weak (µV–mV) and buried in noise, demanding careful acquisition (see [Bioinstrumentation](instrumentation.md)).

## The Processing Pipeline

1. **Acquisition and conditioning** — amplification, [anti-alias filtering](../../signals/sampling.md), digitization.
2. **Denoising** — remove **baseline wander** (high-pass), **powerline interference** (50/60 Hz notch), and motion artifact.
3. **Feature extraction** — detect events and compute features.
4. **Classification / interpretation** — diagnose or control.

## Example: ECG Analysis

The ECG's **QRS complex** marks each heartbeat. **R-peak detection** (e.g. Pan–Tompkins: bandpass → derivative → squaring → integration → thresholding) yields the R-R intervals, from which heart rate and **heart-rate variability (HRV)** are computed. Morphology analysis detects arrhythmias and ischemia.

## Frequency and Time-Frequency Analysis

EEG is analyzed by frequency bands (delta, theta, alpha, beta, gamma) via the [FFT](../../signals/fourier-transform.md). Because biosignals are nonstationary, **time-frequency** methods (spectrograms, wavelets) track how content evolves.

## Machine Learning on Biosignals

Modern systems classify arrhythmias, seizures, and sleep stages with [deep learning](../../cs/ml/deep-learning.md) on raw or feature signals — and decode movement intent from [EMG/EEG](neural.md) for prosthetics and BCIs.

## See Also

- [Signal Processing](../../eng/electrical/signal-processing.md)
- [Bioinstrumentation](instrumentation.md)
- [Neural Engineering](neural.md)
