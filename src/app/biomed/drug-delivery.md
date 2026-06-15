# Drug Delivery and Pharmacokinetics

Drug delivery engineers *how* a therapeutic reaches its target at the right concentration, for the right duration. **Pharmacokinetics (PK)** models what the body does to a drug; **pharmacodynamics (PD)** what the drug does to the body.

## Pharmacokinetics: ADME

A drug's journey is **A**bsorption, **D**istribution, **M**etabolism, **E**limination. The simplest **one-compartment** model treats the body as a single well-mixed volume with first-order elimination:
\\[
\frac{dC}{dt} = -k_e C \;\Rightarrow\; C(t) = C_0 e^{-k_e t},
\\]
giving a **half-life** \\(t_{1/2} = \ln 2 / k_e\\). Multi-compartment models capture distribution to tissues. This is the [compartmental modeling](physiology.md) of [differential equations](../../math/diffeq/first-order.md).

## Key PK Parameters

| Parameter | Meaning |
|---|---|
| Clearance (CL) | volume cleared per time |
| Volume of distribution (V_d) | apparent volume the drug occupies |
| Half-life | time for concentration to halve |
| Bioavailability (F) | fraction reaching circulation |

The **therapeutic window** lies between the minimum effective and maximum safe concentrations — dosing keeps the drug within it.

## Pharmacodynamics

Effect vs. concentration typically follows a saturating (Hill/sigmoid) curve — the same [Michaelis–Menten](../../physics/chemistry/biochemistry.md) form as receptor binding:
\\[
E = \frac{E_{\max} C^n}{EC_{50}^n + C^n}.
\\]

## Controlled-Release Delivery

Engineering controls release kinetics to maintain therapeutic levels and target tissue:
- **Diffusion-controlled** — drug diffuses out of a polymer matrix (Fickian release).
- **Degradation-controlled** — release as a [biodegradable polymer](../materials-science/polymers.md) erodes.
- **Stimuli-responsive** — release triggered by pH, temperature, or enzymes.
- **Targeted delivery** — nanoparticles and antibody conjugates concentrate the drug at disease sites, sparing healthy tissue.

## Closed-Loop Delivery

Devices like the **artificial pancreas** sense glucose and dose insulin via [feedback control](../../eng/control/pid.md) — pharmacology meets [control theory](../../eng/control/README.md).

## See Also

- [Physiological Systems Modeling](physiology.md)
- [First-Order ODEs](../../math/diffeq/first-order.md)
- [Biochemistry](../../physics/chemistry/biochemistry.md)
