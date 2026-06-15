# Joint Modeling

Joints are where motion happens and where loads concentrate. Modeling them — their kinematics, contact, and the tissues that stabilize them — is central to understanding injury, designing implants, and analyzing movement.

## Joint Types and Degrees of Freedom

| Joint type | Example | DOF |
|---|---|---|
| Hinge | elbow, knee (approx.) | 1 |
| Pivot | radioulnar | 1 |
| Ball-and-socket | hip, shoulder | 3 |
| Saddle | thumb CMC | 2 |
| Planar/gliding | intercarpal | varies |

Real joints are not ideal: the knee, for instance, combines rolling, sliding, and rotation, with an instantaneous axis that migrates through the motion.

## Tissues Around a Joint

- **Articular cartilage** — low-friction, load-distributing; viscoelastic and poroelastic.
- **Ligaments** — passive stabilizers; nonlinear stress–strain with a low-stiffness "toe" region.
- **Tendons** — transmit muscle force; nearly elastic energy stores.
- **Synovial fluid** — lubrication (boundary, hydrodynamic, and squeeze-film regimes).

These are **viscoelastic**: response depends on loading rate, with creep, stress relaxation, and hysteresis.

## Joint Mechanics

A joint balances external loads with muscle, ligament, and contact forces. Because muscles act at small moment arms, joint **contact forces** are often several times body weight — the hip can see 3–5× body weight in walking, more when running. This drives implant design and wear analysis.

## Viscoelastic Models

Tissue behavior is captured by spring–dashpot models:
- **Maxwell** (spring + dashpot in series) — stress relaxation.
- **Kelvin–Voigt** (parallel) — creep.
- **Standard linear solid** — both, more realistic.

\\[
\sigma + \tau_\sigma\dot{\sigma} = E(\varepsilon + \tau_\varepsilon\dot{\varepsilon}).
\\]

## Clinical and Engineering Relevance

Joint models predict implant loads and wear, inform ligament-reconstruction surgery, explain osteoarthritis progression, and feed the joint definitions used in [gait analysis](motion.md) and [prosthetic design](prosthetics.md).

## See Also

- [Human Motion](motion.md)
- [Elasticity](../../eng/materials/elasticity.md)
- [Biomaterials](../biomed/biomaterials.md)
