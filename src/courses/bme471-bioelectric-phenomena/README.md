# Bioelectric Phenomena

Nerve and muscle are electrical. Their signals are carried not by electrons in wires but by ions moving through electrolytes and across membranes only a few nanometres thick, and the same physics decides how an electrode records those signals or evokes new ones. This subsection builds that physics from the ground up: from field theory and ion transport, through the Hodgkin–Huxley membrane and the cable equation, to the electrochemistry of electrodes, the amplifiers that record biopotentials, and the rules for exciting tissue safely.

The material follows a graduate course in bioelectric phenomena (BME 471, Part 1). Derivations are given in full where they explain *why* a result holds. Each chapter also keeps the sketches you should be able to draw from memory: in this subject a correct picture of where current flows is usually worth more than the algebra.

## Chapters

1. [Fields, Volume Conductors, and Sources](fields.md): why circuit theory fails for nerve, the gradient, divergence and Laplacian, Poisson's equation, and monopole vs. dipole sources.
2. [Ions, Diffusion, and Membrane Potentials](ions-membranes.md): Nernst–Planck transport, the Einstein relation, the Nernst equilibrium, electroneutrality, and the Goldman–Hodgkin–Katz equation.
3. [The Parallel Conductance Model and the Voltage Clamp](membrane-circuit.md): the membrane as a circuit, driving forces, and how Hodgkin and Huxley separated the Na⁺ and K⁺ currents.
4. [Hodgkin–Huxley Kinetics and Excitation](hodgkin-huxley.md): the m, h and n gates, simulating an action potential, refractoriness, anode break, and current flow around a cathode and an anode.
5. [The Cable Equation and Propagation](cable.md): the core-conductor model, membrane current as curvature, and conduction velocity in unmyelinated and myelinated fibres.
6. [Models of the Node of Ranvier](node-models.md): Frankenhaeuser–Huxley, CRRSS, Schwarz–Eikhof and the human node, and why K⁺ can be dropped for mammalian stimulation models.
7. [The Electrode–Electrolyte Interface](electrode-interface.md): half-cell potentials, polarization, interface impedance, the Warburg models, electrode metals and interface reactions.
8. [Safe Stimulation and Waveform Design](safe-stimulation.md): charge-density limits, constant-current vs. constant-voltage stimulators, charge-balanced biphasic pulses, and electrode shape.
9. [Biopotential Amplifiers](amplifiers.md): the op-amp, the instrumentation amplifier, 60 Hz common-mode interference and CMRR.
10. [Electrical Stimulation of Excitable Tissue](excitation.md): the strength–duration curve, rheobase and chronaxie, accommodation, and the passive cable driven by an extracellular electrode.

## Notation and Sign Conventions

The conventions below are used throughout and match the course notes.

| Symbol | Meaning | Units |
|---|---|---|
| \\(\Phi\_i, \Phi\_e\\) | Intracellular and extracellular potential | V |
| \\(V\_m = \Phi\_i - \Phi\_e\\) | Transmembrane potential | V |
| \\(v\_m = V\_m - V\_{rest}\\) | Membrane potential relative to rest (lower case) | V |
| \\(\vec J\\) | Current density | A/m² |
| \\(\sigma, \rho = 1/\sigma\\) | Conductivity, resistivity | S/m, Ω·m |
| \\(I\_v\\) | Volume source density | A/m³ |
| \\(E\_p\\) | Nernst (equilibrium) potential of ion \\(p\\) | V |
| \\(g\_p, P\_p\\) | Conductance, permeability of ion \\(p\\) | S/cm², cm/s |
| \\(R\_i, R\_m, C\_m\\) | Specific axial resistivity, membrane resistance, membrane capacitance | Ω·cm, Ω·cm², µF/cm² |
| \\(r\_i, r\_e, r\_m, c\_m\\) | The same quantities per unit length of fibre | Ω/cm, Ω/cm, Ω·cm, µF/cm |

- **Positive membrane current is outward** (from inside to outside).
- **Depolarizing** means moving \\(V\_m\\) from rest toward zero (less negative); **hyperpolarizing** means more negative.
- The **anode** is the electrode where current leaves the stimulator and enters the tissue; the **cathode** is where current returns to the stimulator. Biomedical engineers name electrodes by the current *outside* the source; chemists sometimes reverse the names because they look at the current inside the battery.

## Key Results at a Glance

**Fields and sources**
\\[
\vec J = \sigma \vec E = -\sigma\nabla\Phi, \qquad \nabla^2\Phi = -\frac{I\_v}{\sigma}, \qquad
\Phi\_{\text{mono}} = \frac{I\_0}{4\pi\sigma r}, \qquad \Phi\_{\text{dip}} = \frac{p\cos\theta}{4\pi\sigma r^2}
\\]

**Ions and membranes**
\\[
\vec j\_p = -D\_p\left(\nabla C\_p + \frac{z\_p C\_p F}{RT}\nabla\Phi\right), \qquad
E\_p = \frac{RT}{z\_pF}\ln\frac{[C\_p]\_o}{[C\_p]\_i}, \qquad
V\_{rest} = \frac{RT}{F}\ln\frac{P\_K[K]\_o + P\_{Na}[Na]\_o + P\_{Cl}[Cl]\_i}{P\_K[K]\_i + P\_{Na}[Na]\_i + P\_{Cl}[Cl]\_o}
\\]

**Membrane kinetics**
\\[
I\_m = C\_m\frac{dV\_m}{dt} + \bar g\_{Na}m^3h(V\_m - E\_{Na}) + \bar g\_K n^4 (V\_m - E\_K) + g\_L(V\_m - E\_L), \qquad
\frac{dx}{dt} = \alpha\_x(1-x) - \beta\_x x
\\]

**Cable and propagation**
\\[
i\_m = \frac{1}{r\_i + r\_e}\frac{\partial^2 V\_m}{\partial x^2}, \qquad
\lambda = \sqrt{\frac{r\_m}{r\_i + r\_e}} \approx \sqrt{\frac{aR\_m}{2R\_i}}, \qquad
\theta\_{\text{unmyel}} \propto \sqrt{d}, \qquad \theta\_{\text{myel}} \approx 6D\ \text{m/s}\ (D\text{ in µm})
\\]

**Stimulation**
\\[
V\_0 = \frac{V\_T}{1 - e^{-T/\tau}}, \qquad T\_c = \tau\ln 2, \qquad v\_m(x) = -\frac{r\_e \lambda I\_0}{2}e^{-\|x\|/\lambda}
\\]

## Relation to the Rest of the Book

This subsection is the physical foundation for the Neural Engineering chapters: [Electrical Stimulation of Neural Tissue](../neural-control-of-movement/stimulation-theory.md) and [Computational Neural Modeling](../neural-control-of-movement/modeling.md) apply the cable and membrane models developed here, and [Neural Interfaces and Electrodes](../neural-control-of-movement/electrodes.md) builds on the electrode electrochemistry. The mathematics draws on Vector Calculus, Systems of ODEs, Partial Differential Equations and Electrostatics; the instrumentation chapters connect to Bioinstrumentation.
