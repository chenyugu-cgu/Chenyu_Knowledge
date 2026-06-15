# Electromagnetic Waves

Maxwell's equations in free space combine into a wave equation, predicting self-propagating electromagnetic waves — radio, light, X-rays — all the same phenomenon at different frequencies.

## The Wave Equation

In a source-free region, each field component satisfies
\\[
\nabla^2\mathbf{E} = \mu_0\varepsilon_0\frac{\partial^2\mathbf{E}}{\partial t^2},
\\]
a [wave equation](../optics/wave-equation.md) with speed \\(c = 1/\sqrt{\mu_0\varepsilon_0}\\). Solutions are transverse waves with \\(\mathbf{E}\perp\mathbf{B}\perp\) direction of propagation, related by \\(E = cB\\).

## The Electromagnetic Spectrum

| Band | Frequency | Use |
|---|---|---|
| Radio / microwave | kHz–GHz | comms, radar, MRI RF |
| Infrared | THz | thermal imaging |
| Visible | ~430–750 THz | optics, vision |
| UV / X-ray / γ | higher | imaging, sterilization |

All travel at \\(c\\) in vacuum; frequency \\(\times\\) wavelength \\(= c\\).

## Energy and the Poynting Vector

Power flows in the direction of propagation, with intensity
\\[
\mathbf{S} = \frac{1}{\mu_0}\mathbf{E}\times\mathbf{B}.
\\]
The time-averaged magnitude gives the irradiance used in optics and antenna engineering.

## Polarization and Propagation in Media

Waves carry **polarization** (the orientation of \\(\mathbf{E}\\)). In a medium, the speed drops to \\(v = c/n\\) (refractive index \\(n\\)), causing refraction — the link to [geometric](../optics/geometric-optics.md) and [wave optics](../optics/wave-optics.md). Absorption and dispersion vary with frequency.

## Engineering Relevance

Antennas and wireless communication, optical fibers, [medical imaging](../../app/biomed/imaging.md) (X-ray, MRI RF), spectroscopy, and remote sensing all rest on EM-wave physics.

## See Also

- [Maxwell's Equations](maxwell.md)
- [Wave Optics](../optics/wave-optics.md)
- [Fourier Transform](../../signals/fourier-transform.md)
