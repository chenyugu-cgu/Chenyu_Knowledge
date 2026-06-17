# Deep Brain Stimulation and Neuromodulation

Neuromodulation treats neurological and psychiatric disease by **electrically (or chemically) altering** neural activity. It is the most clinically successful application of neural engineering, with hundreds of thousands of implants worldwide.

## Deep Brain Stimulation (DBS)

DBS delivers continuous high-frequency pulses (typically ~130–185 Hz) through electrodes implanted in deep targets:

| Target | Indication |
|---|---|
| Subthalamic nucleus (STN), GPi | Parkinson's disease |
| Ventral intermediate thalamus | essential tremor |
| GPi | dystonia |
| Subgenual cingulate, others | refractory depression, OCD (investigational) |

**Mechanism** remains debated: high-frequency stimulation is thought to disrupt pathological synchronized (e.g. beta-band) activity — a "functional lesion" or network modulation rather than simple excitation or inhibition. The therapeutic effect depends on activating the right axonal pathways, predicted with the [field + axon models](modeling.md) of this subsection.

## The Implantable Pulse Generator (IPG)

The IPG is the device behind DBS, SCS, and VNS: a hermetically sealed, battery-powered (or rechargeable) [microcontroller](../../../eng/mechatronics/microcontrollers.md) driving constant-current stimulation through implanted leads. Programmable parameters — **amplitude, pulse width, frequency, electrode configuration** — are set telemetrically. The same DBS-derived IPG platform, upgraded with real-time wireless control, was repurposed to drive [spinal cord stimulation](spinal-stimulation.md) in the walking-restoration work.

## Vagus Nerve Stimulation (VNS)

A cuff electrode on the vagus nerve, driven by an IPG, treats refractory **epilepsy** and **depression**, and is being explored for inflammation and stroke rehabilitation. It illustrates peripheral neuromodulation via [nerve-cuff electrodes](electrodes.md).

## Responsive (Closed-Loop) Neurostimulation

Open-loop devices stimulate on a fixed schedule. **Responsive neurostimulation (RNS)** for epilepsy instead **records** continuously, **detects** seizure-onset patterns, and **stimulates only when needed** to abort them — a closed loop combining [recording/decoding](recording-decoding.md) with stimulation. **Adaptive DBS** similarly titrates stimulation to a neural biomarker (e.g. beta power in Parkinson's), reducing side effects and saving battery. These are control systems in the literal sense — see [Control Systems](../../../eng/control/README.md).

## Other Modalities

- **Transcranial magnetic stimulation (TMS)** — non-invasive, induces currents via a pulsed magnetic field ([Faraday's law](../../../physics/em/maxwell.md)); used for depression and mapping.
- **Transcranial direct/alternating current stimulation (tDCS/tACS)** — weak scalp currents that modulate excitability.
- **Optogenetics / infrared stimulation** — research tools for cell-type-specific or contactless activation.

## Programming and Trade-offs

Clinicians tune parameters to maximize benefit while avoiding side effects (e.g. spread to adjacent tracts). Current steering across multiple contacts shapes the field, and battery longevity constrains amplitude/frequency — the same [charge and safety limits](electrodes.md) as all stimulation.

## See Also

- [Spinal Cord Stimulation and Neurorehabilitation](spinal-stimulation.md)
- [Neural Recording and Decoding](recording-decoding.md)
- [Electrical Stimulation of Neural Tissue](stimulation-theory.md)
