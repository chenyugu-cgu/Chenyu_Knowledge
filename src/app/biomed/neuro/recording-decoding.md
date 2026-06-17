# Neural Recording and Decoding

Recording captures the nervous system's electrical activity; decoding translates it into meaning — a movement intention, a seizure precursor, a percept. This is the sensing half of every closed-loop neural device and the input to every [brain–computer interface](bci.md).

## What We Record

An electrode picks up the summed extracellular fields of nearby neurons. Spatial scale sets the signal:

| Signal | Source | Bandwidth |
|---|---|---|
| **Action potentials (spikes)** | single-neuron firing | 300 Hz–5 kHz |
| **Local field potential (LFP)** | local synaptic currents | <300 Hz |
| **ECoG** | cortical-surface populations | <500 Hz |
| **EEG** | scalp populations | <100 Hz |
| **EMG** | muscle fibres (M-wave, H-reflex) | 20–500 Hz |

Finer signals require more invasive [electrodes](electrodes.md). All are weak and noisy, demanding the amplification, filtering, and isolation of [bioinstrumentation](../instrumentation.md).

## From Raw Signal to Spikes

For single-unit recording the pipeline is: band-pass filter → threshold detection → **spike sorting** (cluster waveforms by shape, e.g. via PCA + clustering) to attribute spikes to individual neurons. Firing rates are then summarized in time bins or as continuous rates.

## Decoding

A **decoder** maps neural features to an output variable (cursor velocity, limb kinematics, a class label). Common approaches, drawing on [machine learning](../../../cs/ml/README.md):

- **Population vector** — each neuron "votes" in its preferred direction; the weighted sum estimates intended movement.
- **Linear / Wiener filter** — regress kinematics on binned rates.
- **Kalman filter** — model movement as a latent state with neural observations; the standard for continuous cursor/limb control (a state-space estimator — see [Optimal Control](../../../eng/control/optimal.md)).
- **Deep networks (RNNs)** — learn temporal structure end-to-end; current state of the art, including for decoding attempted speech and handwriting.

Decoders must be **calibrated** per session and adapt as signals drift; the user's own neural plasticity helps closed-loop control improve over time.

## Evoked Potentials

Beyond spontaneous activity, we measure responses **evoked** by stimulation: motor evoked potentials (MEPs), somatosensory evoked potentials, and the muscle responses (**M-wave, H-reflex**) used to quantify [fibre recruitment](neurophysiology.md). Recruitment curves — response amplitude vs. stimulus intensity — are the basic readout for evaluating a stimulation paradigm, as in the spinal-stimulation literature.

## Closed-Loop Systems

Recording + decoding + stimulation forms a **closed loop**: detect a brain state and respond. Examples — responsive neurostimulation aborting seizures, adaptive DBS triggered by beta-band biomarkers, and [spatiotemporal spinal stimulation](spinal-stimulation.md) triggered by intended movement. Closed-loop control connects neural engineering directly to [control theory](../../../eng/control/README.md).

## See Also

- [Brain–Computer Interfaces and Motor Prostheses](bci.md)
- [Biosignal Processing](../biosignals.md)
- [Deep Brain Stimulation and Neuromodulation](neuromodulation.md)
