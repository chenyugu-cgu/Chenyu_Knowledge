# Brain–Computer Interfaces and Motor Prostheses

A **brain–computer interface (BCI)** reads neural activity and translates it into commands for an external device — a cursor, a robotic arm, a speller, or the user's own muscles. Motor prostheses restore movement to people with paralysis, amputation, or neuromuscular disease.

## The BCI Pipeline

\\[
\text{record} \to \text{feature extraction} \to \text{decode} \to \text{actuate} \to \text{(feedback)}.
\\]
Each stage was developed earlier in this subsection: [recording](recording-decoding.md), [decoding](recording-decoding.md), and an actuator (screen, robot, or [FES](#functional-electrical-stimulation)). Crucially, **feedback** closes the loop — the user sees the result and adapts, and the decoder is recalibrated.

## Signal Sources

| Source | Invasiveness | Bandwidth / quality |
|---|---|---|
| EEG | non-invasive | low; robust, cheap |
| ECoG | semi-invasive | good; stable |
| Intracortical arrays | invasive | high; single-unit control |

Non-invasive EEG BCIs (e.g. P300 spellers, motor-imagery control) are accessible but limited; intracortical arrays enable high-DOF control of robotic limbs and, recently, fast decoding of attempted handwriting and speech.

## Decoding Movement Intent

Motor-cortex neurons are **directionally tuned**; population activity encodes intended movement. Decoders (population vector, Kalman filter, or [recurrent neural networks](../../../cs/ml/deep-learning.md) — see [Recording and Decoding](recording-decoding.md)) map this activity to continuous kinematics or discrete intent, letting paralyzed users control cursors and arms in real time.

## Functional Electrical Stimulation

Instead of (or in addition to) an external robot, **functional electrical stimulation (FES)** activates the user's *own* paralyzed muscles by stimulating motor nerves — closing the loop from brain to muscle. Systems for ambulation (e.g. surface or implanted multichannel stimulators for paraplegia) and grasp restoration apply the [stimulation physics](stimulation-theory.md) of this subsection. A key limitation is **rapid fatigue** from [reverse, synchronous recruitment](stimulation-theory.md); stimulation strategies and combined BCI–FES "bridges" (decoding intent in cortex, delivering it to muscle or spinal cord) aim to overcome it.

## Bidirectional and Closed-Loop BCIs

Natural movement relies on sensory feedback, so advanced systems also **write** information in — stimulating somatosensory cortex or peripheral nerves to evoke touch, giving the user closed-loop control with sensation. This pairs [recording](recording-decoding.md) and [stimulation](stimulation-theory.md) in one device.

## Challenges

Chronic [electrode](electrodes.md) stability, decoder drift requiring recalibration, generalization across tasks, surgical risk, and the [control-theoretic](../../../eng/control/README.md) problem of stable, intuitive closed-loop behaviour. The field is moving rapidly from lab demonstrations toward clinically deployable systems.

## See Also

- [Neural Recording and Decoding](recording-decoding.md)
- [Spinal Cord Stimulation and Neurorehabilitation](spinal-stimulation.md)
- [Robot Control](../../robotics/control.md), [Prosthetics and Exoskeletons](../../biomechanics/prosthetics.md)
