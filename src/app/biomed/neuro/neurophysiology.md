# Neurophysiology Foundations

Everything in neural engineering rests on how neurons generate and propagate electrical signals, and how those signals organize movement and sensation. This chapter is the biology you need to read the rest of the subsection — and the primary literature.

## The Resting Membrane Potential

A neuron's membrane separates differing ion concentrations (high \\(\text{K}^+\\) inside, high \\(\text{Na}^+\\) and \\(\text{Cl}^-\\) outside). Selective permeability and the Na⁺/K⁺ pump set a **resting potential** of about \\(-70\\) mV, predicted by the **Goldman–Hodgkin–Katz** equation:
\\[
V_m = \frac{RT}{F}\ln\frac{P_K[\text{K}^+]_o + P_{Na}[\text{Na}^+]_o + P_{Cl}[\text{Cl}^-]_i}{P_K[\text{K}^+]_i + P_{Na}[\text{Na}^+]_i + P_{Cl}[\text{Cl}^-]_o}.
\\]
For a single ion this reduces to the **Nernst potential** \\(E_{\text{ion}} = \frac{RT}{zF}\ln\frac{[\text{ion}]_o}{[\text{ion}]_i}\\) — an [electrochemical](../../../physics/chemistry/physical.md) equilibrium.

## The Action Potential

When the membrane depolarizes past **threshold** (~\\(-55\\) mV), voltage-gated Na⁺ channels open explosively, then inactivate as K⁺ channels repolarize — producing the all-or-nothing **action potential (AP)** spike. The biophysics is captured by the [Hodgkin–Huxley model](modeling.md), a set of nonlinear [ODEs](../../../math/diffeq/systems.md) for the membrane voltage and channel gating. A **refractory period** follows, limiting firing rate and enforcing one-way propagation.

## Myelination and Conduction Velocity

Many axons are wrapped in **myelin** with gaps (**nodes of Ranvier**). The AP jumps node to node — **saltatory conduction** — greatly increasing speed. Conduction velocity scales roughly linearly with fibre diameter for myelinated fibres.

| Fibre class | Diameter | Velocity | Function |
|---|---|---|---|
| Aα (Ia, Ib) | 13–20 µm | 80–120 m/s | proprioception, motor (efferent) |
| Aβ (II) | 6–12 µm | 35–75 m/s | touch, muscle spindle |
| Aδ | 1–5 µm | 5–30 m/s | sharp pain, cold |
| C | <1.5 µm (unmyelinated) | <2 m/s | slow pain, autonomic |

Fibre diameter governs not only speed but **excitability to external stimulation** — central to [stimulation theory](stimulation-theory.md).

## Afferent vs. Efferent

- **Afferent** fibres carry signals *toward* the CNS (sensory: proprioception, touch, pain).
- **Efferent** fibres carry commands *away* from the CNS (motor: α-motor neurons to muscle).

This distinction is pivotal for spinal stimulation: recruiting large **proprioceptive afferents** (group Ia) engages spinal circuits and is believed to drive motor recovery, whereas directly recruiting **motor efferents** bypasses those circuits (see [Spinal Cord Stimulation](spinal-stimulation.md)).

## Synapses, Motor Units, and Motor Neuron Pools

Neurons communicate at **synapses** (mostly chemical, via neurotransmitters). A single **α-motor neuron** plus the muscle fibres it innervates is a **motor unit**; the set of motor neurons driving one muscle is a **motor neuron pool**, located in specific spinal segments. Recruiting a pool produces graded muscle force — the variable that spinal and functional electrical stimulation aim to control.

## Reflexes: the H-reflex and M-wave

Stimulating a mixed peripheral nerve evokes two muscle responses used throughout neural engineering as readouts:

- **M-wave** — direct activation of **motor efferents**, short latency.
- **H-reflex** — activation of **Ia proprioceptive afferents** that monosynaptically excite motor neurons (the electrical analogue of the stretch reflex), longer latency.

Because afferents (large, low-threshold) are recruited before efferents at low intensity, the **H-reflex appears first** and the M-wave grows as intensity rises (eventually the antidromic M-volley cancels the H-reflex). The relative size of H vs. M is a direct measure of **afferent vs. efferent recruitment** — exactly the metric used to evaluate spinal stimulation waveforms.

## Spinal Circuits and Central Pattern Generators

The spinal cord is not just a relay: local circuits, including **central pattern generators (CPGs)**, produce rhythmic outputs like stepping. Sensory afferents continuously shape these circuits. This is why engaging afferent pathways — rather than directly driving muscles — can reawaken coordinated locomotion after injury.

## See Also

- [Computational Neural Modeling](modeling.md) — the Hodgkin–Huxley and cable equations.
- [Electrical Stimulation of Neural Tissue](stimulation-theory.md)
- [Biosignal Processing](../biosignals.md) — EMG, including M-wave and H-reflex.
