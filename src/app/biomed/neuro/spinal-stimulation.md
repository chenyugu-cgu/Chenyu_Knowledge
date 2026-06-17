# Spinal Cord Stimulation and Neurorehabilitation

Spinal cord stimulation (SCS) applies electrical current to the spinal cord and its roots. Long used for chronic pain, it has recently achieved something remarkable: helping people with **spinal cord injury (SCI)** stand and walk again. This chapter ties the whole subsection together and provides the background to read the primary literature.

## Why Stimulate the Spinal Cord?

After SCI, descending commands from the brain are interrupted, but the spinal circuitry below the lesion — motor neuron pools and [central pattern generators](neurophysiology.md) — often remains intact. SCS aims to **re-excite and modulate** those circuits so that residual or restored commands can drive coordinated movement.

## The Key Target: Proprioceptive Afferents

The most important insight is *what* gets stimulated. Electrodes over the dorsal (posterior) spinal cord preferentially recruit the large **proprioceptive afferent (Ia) fibres** entering through the **posterior roots** — not the motor neurons directly. Because of [reverse recruitment order](stimulation-theory.md), these large afferents have the lowest thresholds. Engaging them **trans-synaptically** activates motor neuron pools through natural spinal circuits, producing functional, modulable muscle activity. Directly recruiting **motor efferents** instead bypasses these circuits and is far less useful for recovery — the afferent-vs-efferent distinction from [neurophysiology](neurophysiology.md).

## Epidural vs. Transcutaneous

| Modality | Placement | Trade-off |
|---|---|---|
| **Epidural (EES)** | implanted paddle/lead over dura | selective, efficient; requires surgery |
| **Transcutaneous (tSCS)** | skin-surface electrodes | non-invasive; less selective, higher currents |

Both aim to recruit the same posterior-root afferents; the [volume-conductor + axon models](modeling.md) predict how well each does so.

## Spatiotemporal Stimulation: Restoring Walking

Wagner et al. (*Nature*, 2018, "Targeted neurotechnology restores walking in humans with spinal cord injury") combined several ideas from this subsection:

1. **Map the targets** — build motor-neuron activation maps and identify electrode configurations recruiting the posterior roots for each leg muscle group (hip/knee/ankle flexion and extension).
2. **Spatiotemporal sequences** — deliver **spatially selective** bursts whose **timing coincides with the intended phase of gait** (weight acceptance, propulsion, swing), rather than continuous tonic stimulation.
3. **Closed-loop triggering** — an upgraded DBS-derived [implantable pulse generator](neuromodulation.md) with wireless real-time control fires stimulation in sync with movement.
4. **Frequency tuning** — EES frequency grades muscle activity (with the surprising finding that flexor and extensor pools respond differently, reflecting mono- vs. polysynaptic afferent pathways).

Within days this enabled voluntary overground walking; after months of [rehabilitation](../rehab.md), participants regained voluntary control even without stimulation — evidence of **neuroplasticity** and circuit reorganization.

## Waveform Matters: the Kilohertz Question

Keesey et al. (*Nature Biomedical Engineering*, 2026) examine **kilohertz-frequency (kHz) carriers** in transcutaneous SCS. Using peripheral-nerve experiments ([H-reflex/M-wave](neurophysiology.md) recruitment) and the [MRG cable model](modeling.md), they show that kHz waveforms suffer **interrupted subthreshold summation** ([stimulation theory](stimulation-theory.md)): they raise thresholds and **bias recruitment toward motor efferents over the proprioceptive afferents** that drive recovery — especially for cervical tSCS. The lesson: novel waveforms must be analyzed mechanistically, because the *type* of fibre recruited, not just whether muscle twitches, determines therapeutic value.

## Putting It Together

This is why the subsection is ordered as it is: to evaluate a spinal neuroprosthesis you need [fibre physiology](neurophysiology.md), the [recruitment physics](stimulation-theory.md), the [computational models](modeling.md), the [electrodes](electrodes.md), and [recording/closed-loop](recording-decoding.md) control — all at once.

## See Also

- [Deep Brain Stimulation and Neuromodulation](neuromodulation.md)
- [Rehabilitation Devices](../rehab.md), [Prosthetics and Exoskeletons](../../biomechanics/prosthetics.md)
- [Musculoskeletal Modeling](../../biomechanics/musculoskeletal.md)
