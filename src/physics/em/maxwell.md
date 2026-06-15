# Maxwell's Equations

Maxwell's four equations unify electricity, magnetism, and light into a single field theory — one of the supreme achievements of physics.

## The Four Equations (differential form)

\\[
\nabla\cdot\mathbf{E} = \frac{\rho}{\varepsilon_0} \quad\text{(Gauss)},
\\]
\\[
\nabla\cdot\mathbf{B} = 0 \quad\text{(no monopoles)},
\\]
\\[
\nabla\times\mathbf{E} = -\frac{\partial\mathbf{B}}{\partial t} \quad\text{(Faraday)},
\\]
\\[
\nabla\times\mathbf{B} = \mu_0\mathbf{J} + \mu_0\varepsilon_0\frac{\partial\mathbf{E}}{\partial t} \quad\text{(Ampère–Maxwell)}.
\\]

## The Key Insight

Maxwell's addition of the **displacement current** \\(\mu_0\varepsilon_0\,\partial\mathbf{E}/\partial t\\) made the equations consistent and predicted that a changing \\(\mathbf{E}\\) creates \\(\mathbf{B}\\), and vice versa. The two fields sustain each other — **electromagnetic waves** that travel at
\\[
c = \frac{1}{\sqrt{\mu_0\varepsilon_0}} \approx 3\times10^8\ \text{m/s},
\\]
which is the speed of light: **light is an electromagnetic wave**.

## Faraday's Law and Induction

A changing magnetic flux induces an EMF:
\\[
\mathcal{E} = -\frac{d\Phi_B}{dt}.
\\]
This is the basis of generators, transformers, inductive sensors, and MRI signal detection.

## Integral Form

Each differential law has an integral counterpart (flux/circulation over surfaces and loops), often easier for symmetric problems and for connecting to measured voltages and currents.

## From Fields to Circuits

Circuit theory ([Circuit Laws](../../eng/electrical/circuits.md)) is the low-frequency limit of Maxwell's equations, where wavelengths are large compared to the circuit. At high frequencies, full field analysis (transmission lines, waveguides, antennas) is required.

## See Also

- [Electromagnetic Waves](em-waves.md)
- [Electrostatics](electrostatics.md), [Magnetostatics](magnetostatics.md)
- [Vector Calculus](../../math/calculus/vector.md) — divergence and curl theorems.
