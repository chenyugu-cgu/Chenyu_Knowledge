# Transcutaneous Spinal Cord Stimulation

Transcutaneous spinal cord stimulation (**tSCS**) delivers current through **skin-surface electrodes** over the spine, recruiting the same posterior-root afferents as implanted [epidural stimulation (EES)](spinal-stimulation.md) but **without surgery**. Its accessibility has made it a fast-growing tool for motor recovery after [spinal cord injury](spinal-cord-injury.md) — and the subject of the Keesey et al. (2026) study. This chapter covers what makes tSCS work and how its mechanisms are verified.

## Electrode Montage

A typical lumbar montage places the **cathode(s)** on the midline over the **T11–L1 vertebrae** (above the lumbosacral cord) and large **anode(s)** on the abdomen or iliac crests. For the arms/hands, a **cervical** montage places cathodes over the cervical spine with anodes on the clavicles or iliac crests. Because current must cross skin, fat (**subcutaneous adipose tissue**), and bone before reaching the cord, tSCS needs **much higher currents** than EES and current spreads more — the [volume-conductor problem](modeling.md) with low-conductivity layers in the path.

## The Target: Posterior-Root Afferents

Like EES, lumbar tSCS preferentially recruits the large **proprioceptive afferent (Ia) fibres** in the **posterior roots** (lowest threshold by [reverse recruitment order](stimulation-theory.md)). These engage motor neuron pools **trans-synaptically**, evoking **posterior root-muscle (PRM) reflexes** — the surface analogue of the [H-reflex](neurophysiology.md). Engaging afferents (rather than directly driving motor efferents) is believed to be what makes tSCS therapeutic, because it recruits the spinal circuits that organize movement.

## Proving Afferent Recruitment

How do you know stimulation recruited *afferents* (good) versus *motor efferents* directly (bypassing circuits)? Three converging tests, all used in the literature:

1. **Post-activation (paired-pulse) depression.** Deliver two identical pulses a short interval apart. A response mediated by the **monosynaptic Ia→motor neuron** synapse is **suppressed** on the second pulse (homosynaptic / low-frequency depression — see [Neurophysiology](neurophysiology.md)); a directly evoked motor response is **not**. Strong paired-pulse suppression therefore confirms an **afferent (reflex)** origin. Keesey et al. use this and find conventional waveforms produce ~22% suppression vs. only ~5% for kHz — evidence kHz recruits more direct motor efferents.
2. **Response latency.** Afferent-mediated (trans-synaptic) responses arrive **later** than the peripheral conduction time; direct motor-efferent responses arrive **at or before** it (compared against M-wave/**F-wave** conduction times — see [Recording and Decoding](recording-decoding.md)).
3. **Hmax/Mmax ratio.** A larger maximal reflex relative to the maximal direct response indicates stronger afferent engagement.

## Lumbar vs. Cervical

A key finding: recruitment differs by site. **Lumbar** tSCS recruits mainly **posterior-root afferents**, whereas **cervical** tSCS tends to recruit **anterior-root motor efferents** directly — regardless of waveform. So the afferent-engagement strategy that works for the legs translates less cleanly to the arms, a caution for cervical neurorehabilitation.

## The Kilohertz-Frequency Question

Some tSCS protocols use a **kilohertz-frequency (kHz) carrier** (e.g. 10 kHz bursts), originally adopted on the assumption it improves comfort. Keesey et al. show the trade-off is real and unfavourable for the *mechanism*:

- kHz waveforms suffer **interrupted subthreshold summation** ([stimulation theory](stimulation-theory.md)) — each cycle's depolarization is partly cancelled by the next phase's hyperpolarization — so they **raise thresholds**.
- Because the effect differs by fibre type, kHz **biases recruitment toward motor efferents over proprioceptive afferents**, exactly the wrong direction for engaging spinal circuits — worst in cervical tSCS.
- Their [MRG-model](modeling.md) simulations and [H-reflex/M-wave](neurophysiology.md) experiments agree, and suggest the response is dominated by the **first biphasic sub-pulse**, making the kHz "carrier" largely incidental.

**Takeaway:** a waveform that produces muscle twitches is not necessarily engaging the therapeutic pathway. Verifying *which fibres* are recruited — via paired-pulse depression, latency, and modeling — is essential before adopting novel tSCS paradigms.

## tSCS vs. EES

| | tSCS | EES |
|---|---|---|
| Invasiveness | non-invasive (surface) | implanted lead |
| Selectivity | lower (current spreads) | high (close to roots) |
| Current required | high (crosses skin/fat) | low |
| Closed-loop timing | harder | demonstrated (spatiotemporal) |
| Access / cost | broad | surgical |

## See Also

- [Spinal Cord Stimulation and Neurorehabilitation](spinal-stimulation.md) — implanted EES and spatiotemporal stimulation.
- [Spinal Cord Injury](spinal-cord-injury.md), [Electrical Stimulation of Neural Tissue](stimulation-theory.md)
- [Computational Neural Modeling](modeling.md)
