# Medical Imaging

Medical imaging visualizes the interior of the body non-invasively. Each modality exploits a different physical interaction and a different reconstruction mathematics — a beautiful applied showcase of [signals and systems](../../signals/fundamentals.md).

## Modalities at a Glance

| Modality | Physics | Reconstruction | Strength |
|---|---|---|---|
| X-ray | attenuation of X-rays | projection | bone, fast |
| CT | rotating X-ray | inverse Radon transform | 3-D anatomy |
| MRI | nuclear magnetic resonance | inverse Fourier (k-space) | soft tissue, no ionizing radiation |
| Ultrasound | reflected sound (echo timing) | beamforming | real-time, safe, cheap |
| PET/SPECT | gamma from radiotracers | tomographic | function/metabolism |

## Computed Tomography (CT)

CT acquires X-ray **projections** at many angles and reconstructs a cross-section by inverting the **Radon transform**, typically via **filtered back-projection**:
\\[
f(x,y) = \int_0^\pi \big(p_\theta * h\big)(x\cos\theta + y\sin\theta)\,d\theta,
\\]
where \\(p_\theta\\) is the projection at angle \\(\theta\\) and \\(h\\) a ramp filter. Iterative and deep-learning reconstruction now reduce dose.

## Magnetic Resonance Imaging (MRI)

MRI manipulates the spin of hydrogen nuclei with magnetic field gradients, sampling the spatial **Fourier transform** of the image (**k-space**). The image is recovered by an inverse 2-D FFT:
\\[
I(x,y) = \mathcal{F}^{-1}\{S(k_x, k_y)\}.
\\]
Contrast is tuned by pulse-sequence timing (T1, T2, diffusion), making MRI superb for soft tissue. This is the [Fourier transform](../../signals/fourier-transform.md) made literally visible.

## Ultrasound

Pulses of high-frequency sound reflect at tissue interfaces; depth comes from echo time \\(d = ct/2\\). **Beamforming** across a transducer array focuses and steers the beam. Doppler shift measures blood-flow velocity. Safe, portable, real-time — but limited by bone and air.

## Image Processing and AI

Reconstruction is only the start: denoising, segmentation, registration, and increasingly **deep-learning** diagnosis (detection, classification) extract clinical meaning. See [Deep Learning](../../cs/ml/deep-learning.md).

## See Also

- [Fourier Transform](../../signals/fourier-transform.md)
- [Signal Processing](../../eng/electrical/signal-processing.md)
- [Sampling and Reconstruction](../../signals/sampling.md)
