# Spinal Cord Injury

Spinal cord injury (SCI) is the clinical problem that motivates much of modern neural engineering. Understanding *what* is damaged — and crucially *what survives* — is the key to understanding why electrical stimulation can restore movement.

## Anatomy and Levels

The spinal cord runs from the brainstem to roughly the L1–L2 vertebra, where it tapers into the **conus medullaris**; below that, the nerve roots form the **cauda equina**. Thirty-one paired **spinal nerves** exit through roots — **posterior (dorsal) roots** carry sensory **afferents** in, **anterior (ventral) roots** carry motor **efferents** out (see [Neurophysiology Foundations](neurophysiology.md)).

Injury level is named by the lowest intact segment:

| Region | Segments | Function lost below |
|---|---|---|
| Cervical | C1–C8 | tetraplegia (arms + legs) |
| Thoracic | T1–T12 | paraplegia (trunk + legs) |
| Lumbosacral | L1–S5 | legs, bladder/bowel |

The **lumbosacral** cord (segments L1–S2) houses the motor neuron pools for the legs — the target of spinal stimulation for walking.

## Completeness: the ASIA Impairment Scale

Injuries are graded by the **ASIA Impairment Scale (AIS)**, based on a standardized exam of motor and sensory function across **myotomes** (muscles per segment) and **dermatomes** (skin areas per segment):

| AIS | Description |
|---|---|
| A | **Complete** — no motor or sensory function in sacral segments S4–S5 |
| B | sensory but not motor function preserved below |
| C / D | **motor incomplete** — voluntary motor preserved, mostly weak (C) or functional (D) |
| E | normal |

The **lower extremity motor score (LEMS)** sums strength (0–5) across key leg muscles — a quantitative outcome used to track recovery (the metric that improved by 11–16 points in the spatiotemporal-EES study).

## Upper vs. Lower Motor Neuron

- **Upper motor neuron (UMN)** lesions (the cord/brain) spare the spinal reflex arcs below, producing **spasticity**, hyperreflexia, and intact (often exaggerated) reflexes.
- **Lower motor neuron (LMN)** lesions (anterior horn, roots, peripheral nerve) abolish reflexes and cause flaccid paralysis and atrophy.

This distinction matters enormously for neuromodulation: it works precisely because most SCI is a **UMN** lesion that leaves the **spinal circuitry, motor neuron pools, and afferent inputs below the lesion intact** — they are simply disconnected from descending control.

## Why Neuromodulation Can Help

The central premise of [spinal cord stimulation](spinal-stimulation.md): the machinery for stepping — motor neuron pools, [central pattern generators](neurophysiology.md), and proprioceptive feedback loops — survives below the injury. Stimulation re-excites and modulates this dormant circuitry so that residual descending signals (in incomplete injury) or the circuits themselves can again produce movement. Months of stimulation-enabled training then drive **neuroplasticity** — strengthening spared pathways and, remarkably, restoring some voluntary control even without stimulation.

## Acute vs. Chronic; Spinal Shock

Immediately after injury, **spinal shock** suppresses reflexes for days to weeks. **Chronic** SCI (the population in neuroprosthetic studies, typically years post-injury) has stable, often hyperreflexic circuits below the lesion — the substrate neuromodulation engages.

## Secondary Complications

Beyond paralysis, SCI affects bladder/bowel, blood pressure (autonomic dysreflexia), respiration (high cervical), pressure injuries, and bone density — all targets for biomedical engineering, and all reasons restoring even partial function matters.

## See Also

- [Spinal Cord Stimulation and Neurorehabilitation](spinal-stimulation.md)
- [Transcutaneous Spinal Cord Stimulation](tscs.md)
- [Rehabilitation Devices](../rehab.md), [Musculoskeletal Modeling](../../biomechanics/musculoskeletal.md)
