# Neural Engineering

Neural engineering applies engineering principles to **understand, interface with, repair, and augment** the nervous system. It spans the electrophysiology of single neurons, the physics of stimulating excitable tissue, the electrodes and electronics that form neural interfaces, and the devices — deep brain stimulators, spinal cord stimulators, cochlear and retinal implants, and brain–computer interfaces — that treat disease and restore lost function.

This is the most interdisciplinary corner of biomedical engineering, drawing on [electromagnetism](../../physics/em/README.md), [differential equations](../../math/diffeq/README.md), [signal processing](../../eng/electrical/signal-processing.md), [control](../../eng/control/README.md), [materials](biomaterials.md), and [machine learning](../../cs/ml/README.md).

## How to Read This Subsection

The chapters build from biology to devices, so that by the end you can read the primary literature — clinical trials of spinal-cord neuroprostheses, computational models of fibre recruitment, and neuromodulation studies — and follow the mechanisms.

| Chapter | What it gives you |
|---|---|
| [Neurophysiology Foundations](neuro/neurophysiology.md) | the action potential, fibre types, reflexes (H-reflex, M-wave), motor pools |
| [Electrical Stimulation of Neural Tissue](neuro/stimulation-theory.md) | activating function, strength–duration, recruitment order, kHz waveforms |
| [Computational Neural Modeling](neuro/modeling.md) | Hodgkin–Huxley, cable theory, the MRG axon model, volume-conductor FEM |
| [Neural Interfaces and Electrodes](neuro/electrodes.md) | electrode–tissue interface, safe charge injection, array technologies |
| [Neural Recording and Decoding](neuro/recording-decoding.md) | spikes/LFP/ECoG/EEG, spike sorting, decoders |
| [Deep Brain Stimulation and Neuromodulation](neuro/neuromodulation.md) | DBS, VNS, responsive neurostimulation, the implantable pulse generator |
| [Spinal Cord Injury](neuro/spinal-cord-injury.md) | injury levels, ASIA completeness, UMN/LMN, surviving circuits |
| [Spinal Cord Stimulation and Neurorehabilitation](neuro/spinal-stimulation.md) | epidural EES, spatiotemporal stimulation, restoring walking (Wagner 2018) |
| [Transcutaneous Spinal Cord Stimulation](neuro/tscs.md) | montages, PRM reflexes, proving afferent recruitment, the kHz problem (Keesey 2026) |
| [Sensory Prostheses](neuro/sensory-prostheses.md) | cochlear and retinal implants |
| [Brain–Computer Interfaces and Motor Prostheses](neuro/bci.md) | decoding intent, FES, neuroprosthetic control |

## The Two Verbs: Record and Stimulate

Almost everything in neural engineering is built from two operations:

- **Recording** — transducing the tiny ionic currents of neurons into electronic signals we can measure and decode ([Recording and Decoding](neuro/recording-decoding.md)).
- **Stimulation** — injecting controlled current to evoke or modulate neural activity ([Stimulation Theory](neuro/stimulation-theory.md)).

A **closed-loop** system does both: it senses neural or behavioural state and adjusts stimulation in response — the frontier of responsive epilepsy therapy, adaptive DBS, and spatiotemporal spinal stimulation.

## Further Reading

The textbook *Neuroengineering* (DiLorenzo & Bronzino, CRC Press, 2008) surveys the clinical field. Landmark recent work includes Wagner et al., "Targeted neurotechnology restores walking in humans with spinal cord injury" (*Nature*, 2018), and Keesey et al. on kilohertz-frequency limitations in transcutaneous spinal cord stimulation (*Nature Biomedical Engineering*, 2026). See the [Bibliography](../../appendix/bibliography.md).

## See Also

- [Biosignal Processing](biosignals.md)
- [Rehabilitation Devices](rehab.md)
- [Prosthetics and Exoskeletons](../biomechanics/prosthetics.md)
