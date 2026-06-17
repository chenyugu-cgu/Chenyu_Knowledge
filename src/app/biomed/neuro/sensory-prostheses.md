# Sensory Prostheses

Sensory prostheses **replace a lost sense** by transducing external stimuli into patterned electrical stimulation of the surviving neural pathway. They are the most successful neural interfaces in clinical use.

## The Cochlear Implant

The cochlear implant restores hearing to people with sensorineural deafness by bypassing damaged hair cells and stimulating the **auditory nerve** directly. The signal chain:

1. **Microphone** captures sound.
2. **Filter bank** splits it into frequency bands (a [Fourier](../../../signals/fourier-transform.md)-domain decomposition).
3. **Envelope extraction** per band estimates loudness.
4. **Electrode array** (typically 12–22 contacts) in the cochlea stimulates auditory-nerve regions **tonotopically** — basal contacts for high frequencies, apical for low — exploiting the cochlea's place-frequency map.

It works because the cochlea already maps frequency to position; the implant injects current at the matching place. Speech-processing strategies (e.g. continuous interleaved sampling) interleave pulses across electrodes to limit channel interaction. Over a hundred thousand recipients hear well enough to use the telephone — neural engineering's clearest success.

## Visual Prostheses

Restoring vision is harder because the visual system has no simple 1-D map. Approaches stimulate at different stages:

- **Retinal implants** (epiretinal/subretinal) stimulate surviving retinal ganglion or bipolar cells in degenerative disease (retinitis pigmentosa), driven by a camera. They evoke **phosphenes** (spots of light) forming a coarse image.
- **Cortical visual prostheses** stimulate visual cortex directly, bypassing the eye and optic nerve entirely.

Resolution is limited by electrode count and density and by [charge-density safety limits](electrodes.md); current devices restore only crude vision (light/motion, large shapes), and increasing useful resolution is the central challenge.

## Common Engineering Themes

- **Transduction** — sensor → signal processing → stimulation pattern.
- **Exploiting existing maps** — tonotopy (cochlea), retinotopy (visual system).
- **Channel count vs. selectivity** — more electrodes promise more information but face crosstalk and [charge limits](electrodes.md).
- **The brain adapts** — recipients learn to interpret unnatural input, a [plasticity](spinal-stimulation.md) effect central to outcomes.

## See Also

- [Neural Interfaces and Electrodes](electrodes.md)
- [Electrical Stimulation of Neural Tissue](stimulation-theory.md)
- [Acoustics](../../../physics/optics/acoustics.md), [Geometric Optics](../../../physics/optics/geometric-optics.md)
