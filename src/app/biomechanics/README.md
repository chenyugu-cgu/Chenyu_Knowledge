# Biomechanics

Biomechanics applies the principles of mechanics to living systems — bones, muscles, joints, tissues, and whole-body movement. It bridges [dynamics](../../eng/dynamics/README.md), [strength of materials](../../eng/materials/README.md), and physiology, and underpins prosthetics, rehabilitation, sports science, and ergonomics.

## Scope

- **Kinematics of movement** — describing how the body moves (gait, reaching). See [Human Motion](motion.md).
- **Kinetics** — the forces and moments that cause movement (muscle forces, joint loads, ground reaction).
- **Tissue mechanics** — how bone, cartilage, tendon, and muscle deform and fail.
- **Devices** — prosthetics, orthoses, and exoskeletons that restore or augment function. See [Prosthetics and Exoskeletons](prosthetics.md).

## What Makes Biological Mechanics Special

- **Composite, anisotropic, viscoelastic tissues** — properties depend on direction, rate, and history.
- **Active actuation** — muscles generate force and adapt.
- **Self-repair and adaptation** — bone remodels to load (Wolff's law).
- **Large inter-individual variability** — models must be patient-specific.

## The Analysis Pipeline

1. **Capture** motion (optical markers, IMUs) and forces (force plates, EMG).
2. **Model** the body as linked rigid segments with joints.
3. **Inverse dynamics** — compute joint moments from motion + external forces.
4. **Interpret** — relate to function, injury risk, or device design.

## Chapter Map

- [Human Motion](motion.md)
- [Joint Modeling](joints.md)
- [Prosthetics and Exoskeletons](prosthetics.md)
- [Tissue Mechanics](tissue.md) — viscoelastic, anisotropic biological tissue.
- [Musculoskeletal Modeling](musculoskeletal.md) — muscle forces and joint loads.
- [Ergonomics and Injury](ergonomics.md) — designing to fit the body.

This section connects to [Robotics](../robotics/README.md) (the body as a linkage) and [Biomedical Engineering](../biomed/README.md).
