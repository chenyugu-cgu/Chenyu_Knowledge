# Electrical Stimulation of Neural Tissue

How does an electrode outside a neuron make it fire? This chapter is the physics of **functional electrical stimulation** — the foundation for understanding deep brain stimulation, spinal cord stimulation, and every neuroprosthesis. It is also the theory the recent spinal-stimulation papers build on.

## The Activating Function

An extracellular electrode sets up a potential field \\(V_e(x)\\) in tissue. Along an axon, what drives the membrane is not the potential itself but its **second spatial derivative** — the **activating function** (Rattay):
\\[
f(x) \propto \frac{\partial^2 V_e}{\partial x^2}.
\\]
Where \\(\partial^2 V_e/\partial x^2 > 0\\) the membrane depolarizes (and can fire); where it is negative, it hyperpolarizes. This is why axons are most excitable at **bends, terminals, and nodes**, and why a cathode (current sink) depolarizes nearby axons. It falls directly out of the [cable equation](modeling.md).

## Strength–Duration Relationship

The stimulus charge needed to reach threshold depends on pulse **duration**. The classic **Weiss/Lapicque** strength–duration curve:
\\[
I_{th}(t) = I_{rh}\left(1 + \frac{t_{ch}}{t}\right),
\\]
where \\(I_{rh}\\) is the **rheobase** (threshold current for an infinitely long pulse) and \\(t_{ch}\\) is the **chronaxie** (the duration at which threshold current is twice rheobase). Short pulses need more current but less *charge*; long pulses the reverse. Chronaxie is a fibre fingerprint — larger, more excitable fibres have shorter chronaxie.

## Recruitment Order: Large Fibres First

Crucially, electrical stimulation recruits fibres in the **reverse of natural order**: **large-diameter fibres have lower thresholds** and are recruited first, small fibres last. Two consequences:

- In a mixed nerve, large **proprioceptive afferents (Ia)** and large motor efferents activate before small fibres — and at low intensity the [H-reflex precedes the M-wave](neurophysiology.md).
- In [FES](bci.md), this "reverse recruitment" plus synchronous firing causes rapid fatigue, unlike physiological recruitment of small units first.

Threshold also falls with proximity to the electrode (the field, and its second derivative, are larger nearby).

## Waveforms and Charge Balance

Practical stimulation uses **biphasic, charge-balanced** pulses: a cathodic phase to excite, followed by an equal anodic phase to reverse electrochemical reactions and avoid tissue/electrode damage (see [Electrodes](electrodes.md)). Monophasic pulses inject net charge and are unsafe for chronic use.

## Kilohertz-Frequency Stimulation

Recent transcutaneous spinal stimulation uses **kilohertz-frequency (kHz) carriers**. Two distinct phenomena arise:

- **Conduction block** — sustained kHz current can *block* axons by holding gates inactivated.
- **Subthreshold summation** — for kHz *bursts*, each cycle's brief depolarization is partly undone by the next phase's hyperpolarization, so many cycles must summate to reach threshold ("interrupted subthreshold summation"). The result: **kHz waveforms raise thresholds** and, because the effect differs across fibre types, **bias recruitment toward motor efferents over proprioceptive afferents**.

This is precisely the mechanism Keesey et al. (2026) identify as a limitation of kHz transcutaneous spinal stimulation — see [Spinal Cord Stimulation](spinal-stimulation.md). Understanding it requires the activating function, strength–duration behaviour, and a [biophysical axon model](modeling.md).

## Selectivity

Engineering goals — activating the *right* fibres and sparing others — are pursued by electrode geometry (multipolar, current steering), pulse shape (e.g. prepulses, slow rising ramps to invert recruitment order), and timing. Selectivity is what separates a crude shock from a useful neuroprosthesis.

## See Also

- [Computational Neural Modeling](modeling.md) — predicting all of the above.
- [Neural Interfaces and Electrodes](electrodes.md) — charge injection limits.
- [Spinal Cord Stimulation and Neurorehabilitation](spinal-stimulation.md)
