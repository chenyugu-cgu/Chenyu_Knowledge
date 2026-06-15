# Acoustics

Acoustics is the science of sound — pressure waves in a medium. It is central to ultrasound imaging, audio engineering, noise control, and the [vibration](../../eng/dynamics/vibrations.md) of structures.

## Sound Waves

Sound is a **longitudinal** pressure wave. Its speed depends on the medium's stiffness and density:
\\[
c = \sqrt{\frac{B}{\rho}} \approx 343\ \text{m/s in air}, \quad \approx 1480\ \text{m/s in water/tissue}.
\\]
The much higher speed in tissue is why ultrasound resolves fine anatomy.

## Intensity and the Decibel Scale

Sound intensity spans an enormous range, so it is measured logarithmically:
\\[
L = 10\log_{10}\frac{I}{I_0}\ \text{dB}, \qquad I_0 = 10^{-12}\ \text{W/m}^2.
\\]
Every +10 dB is ten times the intensity; +3 dB is a doubling.

## The Doppler Effect

Relative motion shifts the observed frequency:
\\[
f' = f\,\frac{c \pm v_{\text{observer}}}{c \mp v_{\text{source}}}.
\\]
**Doppler ultrasound** measures blood-flow velocity from the frequency shift of echoes — a core [hemodynamics](../../app/biomed/hemodynamics.md) tool.

## Ultrasound and Imaging

High-frequency sound (1–15 MHz) reflects at tissue interfaces; echo timing gives depth (\\(d = ct/2\\)) and beamforming forms images. Higher frequency → finer resolution but shallower penetration. See [Medical Imaging](../../app/biomed/imaging.md).

## Resonance and Acoustic Modes

Cavities and pipes resonate at discrete frequencies (organ pipes, the vocal tract, room modes). The same modal analysis applies to [structural vibration](../../eng/dynamics/vibrations.md).

## Applications

Medical ultrasound, sonar, audio and music, architectural acoustics, noise and vibration control, and nondestructive testing.

## See Also

- [The Wave Equation](wave-equation.md)
- [Biofluid Mechanics and Hemodynamics](../../app/biomed/hemodynamics.md)
- [Sampling and Reconstruction](../../signals/sampling.md)
