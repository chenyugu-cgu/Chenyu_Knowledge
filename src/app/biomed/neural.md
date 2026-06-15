# Neural Engineering

Neural engineering interfaces with the nervous system to **record** neural activity and **stimulate** it — restoring sensation and movement, treating disorders, and building brain-computer interfaces (BCIs).

## The Neural Signal

Neurons communicate via **action potentials** — voltage spikes propagating along axons, governed by ion channels and modeled by the **Hodgkin–Huxley** equations (a set of nonlinear [ODEs](../../math/diffeq/systems.md)). These bioelectric signals are what we record and modulate, rooted in [electromagnetism](../../physics/em/electrostatics.md) and electrochemistry.

## Recording

| Modality | Scale | Invasiveness |
|---|---|---|
| EEG | populations (scalp) | non-invasive |
| ECoG | cortical surface | semi-invasive |
| Microelectrode arrays | single neurons | invasive |

Recorded signals are processed (spike sorting, [biosignal](biosignals.md) methods) and **decoded** — translating neural activity into intent.

## Stimulation

Applying controlled current excites neurons:
- **Deep brain stimulation (DBS)** — treats Parkinson's, tremor.
- **Cochlear implants** — restore hearing by stimulating the auditory nerve.
- **Retinal/visual prostheses** — restore rudimentary vision.
- **Functional electrical stimulation (FES)** — activate paralyzed muscles (see [Rehabilitation Devices](rehab.md)).

Safe stimulation respects charge-density limits to avoid tissue damage.

## Brain-Computer Interfaces

BCIs decode neural intent to control external devices — cursors, [prosthetic limbs](../biomechanics/prosthetics.md), or communication aids. The pipeline is signal acquisition → feature extraction → [machine-learning](../../cs/ml/README.md) decoder → device command, often with feedback enabling the user to adapt. Decoding movement intent from motor cortex restores function for paralyzed users.

## Challenges

Biocompatibility and long-term stability of electrodes ([Biomaterials](biomaterials.md)), the tiny and noisy signals, the brain's plasticity, and rigorous safety/ethics — neural engineering sits at the frontier of biomedical engineering.

## See Also

- [Biosignal Processing](biosignals.md)
- [Rehabilitation Devices](rehab.md)
- [Prosthetics and Exoskeletons](../biomechanics/prosthetics.md)
