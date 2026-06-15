# Mechanical Design

Mechanical design turns analysis into hardware: selecting and sizing the components that transmit motion and force, and specifying them precisely enough to manufacture. It synthesizes [statics](../statics/README.md), [dynamics](../dynamics/README.md), [strength of materials](../materials/README.md), and [materials science](../../app/materials-science/README.md).

## The Design Process

1. **Define** requirements, loads, and constraints.
2. **Conceptualize** mechanisms and architectures.
3. **Analyze** stresses, deflections, fatigue, and kinematics.
4. **Select** standard components and materials.
5. **Specify** dimensions and tolerances for manufacture.
6. **Verify** with prototypes, testing, and iteration.

## Design Against Failure

Every component is sized with a **factor of safety**:
\\[
n = \frac{\text{strength}}{\text{working stress}} > 1,
\\]
accounting for uncertainty in loads, materials, and analysis. Fatigue (cyclic loading) governs most rotating machinery — see [Failure Theories](../materials/failure.md).

## Chapter Map

- [Machine Elements](machine-elements.md) — shafts, springs, fasteners, bearings.
- [Mechanisms and Linkages](mechanisms.md) — converting and transmitting motion.
- [Power Transmission](power-transmission.md) — gears, belts, chains.
- [Tolerancing and GD&T](tolerancing.md) — specifying fit and function.

## Connections

Mechanical design feeds directly into [Mechatronics](../mechatronics/README.md) and [Robotics](../../app/robotics/README.md), where mechanism design meets sensing and control.
