# Magnetostatics

Magnetostatics treats magnetic fields produced by **steady** currents.

## The Magnetic Field of Currents

Moving charges create magnetic fields. The **Biot–Savart law** gives the field of a current element,
\\[
d\mathbf{B} = \frac{\mu_0}{4\pi}\frac{I\,d\boldsymbol{\ell}\times\hat{\mathbf{r}}}{r^2},
\\]
and **Ampère's law** relates the field circulation to the enclosed current:
\\[
\oint_C \mathbf{B}\cdot d\boldsymbol{\ell} = \mu_0 I_{\text{enc}}, \qquad \nabla\times\mathbf{B} = \mu_0\mathbf{J}.
\\]

## Key Results

- **Long straight wire:** \\(B = \dfrac{\mu_0 I}{2\pi r}\\).
- **Solenoid (n turns/length):** \\(B = \mu_0 n I\\) inside, ~0 outside.
- **No magnetic monopoles:** \\(\nabla\cdot\mathbf{B} = 0\\) — field lines always close.

## Force on Currents

A current in a field feels a force \\(\mathbf{F} = I\boldsymbol{\ell}\times\mathbf{B}\\); parallel currents attract. This is the operating principle of **electric motors** and loudspeakers — see [Actuators](../../eng/mechatronics/actuators.md).

## Inductance and Magnetic Energy

A changing current stores energy in its magnetic field; self-inductance \\(L\\) gives
\\[
U = \tfrac12 L I^2.
\\]
Inductance shapes circuit dynamics ([AC and DC Analysis](../../eng/electrical/ac-dc.md)) and enables transformers and wireless power.

## Magnetic Materials

Materials respond to fields as diamagnetic, paramagnetic, or **ferromagnetic** (iron, with hysteresis and saturation). Ferromagnets concentrate flux in motors, transformers, and magnetic recording, and the strong fields in [MRI](../../app/biomed/imaging.md).

## See Also

- [Electrostatics](electrostatics.md)
- [Maxwell's Equations](maxwell.md)
- [Semiconductors](../../eng/electrical/semiconductors.md)
