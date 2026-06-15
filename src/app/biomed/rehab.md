# Rehabilitation Devices

Rehabilitation engineering designs technology that restores, replaces, or augments lost physical function — helping people recover from injury, stroke, or disability and live independently.

## Categories

- **Prosthetics** — replace missing limbs. See [Prosthetics and Exoskeletons](../biomechanics/prosthetics.md).
- **Orthotics** — support or correct existing limbs (braces, AFOs).
- **Exoskeletons** — wearable robots that assist movement or support rehabilitation therapy.
- **Functional electrical stimulation (FES)** — electrically activate paralyzed muscles.
- **Assistive technology** — wheelchairs, communication aids, environmental controls.
- **Neural interfaces** — brain–computer interfaces (BCIs) that translate neural activity into device commands.

## Design Principles

- **User-centered** — function, comfort, weight, appearance, and ease of use determine adoption as much as raw performance.
- **Robust and safe** — devices operate unsupervised in daily life.
- **Affordable and maintainable** — accessibility matters globally.
- **Adaptable** — patients' abilities change over time and during recovery.

## Intent Detection and Control

The hardest problem is reading what the user wants:
- **EMG / myoelectric** — surface electrodes; pattern recognition classifies intent.
- **Brain–computer interfaces** — decode motor intent from EEG or implanted electrodes.
- **Sensor-driven state machines** — switch assistance by detected activity (sitting, walking, stairs).

Modern systems lean heavily on [machine learning](../../cs/ml/README.md) to map noisy biosignals to reliable commands, and on [control theory](../../eng/control/README.md) for safe, transparent assistance.

## Neuroplasticity and Therapy

Rehabilitation robots also **drive recovery**: repetitive, intensive, feedback-rich movement promotes neuroplasticity after stroke or spinal injury. Robotic therapy delivers high-dose, measurable practice and gamified motivation, with sensors tracking progress objectively.

## Functional Electrical Stimulation

FES applies controlled current to elicit muscle contraction, restoring grasp, standing, or cycling in paralysis. Closed-loop FES uses feedback to modulate stimulation against muscle fatigue — a direct application of [feedback control](../../eng/control/pid.md).

## See Also

- [Prosthetics and Exoskeletons](../biomechanics/prosthetics.md)
- [Robot Control](../robotics/control.md)
- [Human Motion](../biomechanics/motion.md)
