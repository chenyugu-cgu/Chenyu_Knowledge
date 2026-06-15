# Mechanical Properties

Mechanical properties quantify how a material responds to forces. They are measured by standardized tests and feed directly into [strength-of-materials](../../eng/materials/README.md) design.

## Stiffness and Strength

- **Elastic modulus** \\(E\\) — stiffness, the slope of the elastic stress–strain region (a structure-insensitive property set by bonding).
- **Yield strength** \\(\sigma_y\\) — onset of permanent deformation.
- **Ultimate tensile strength** \\(\sigma_u\\) — maximum stress before failure.

These come from the **tension test** — see [Stress and Strain](../../eng/materials/stress-strain.md).

## Ductility and Toughness

- **Ductility** — capacity for plastic deformation, reported as % elongation or % reduction in area.
- **Toughness** — energy absorbed before fracture, the **area under the stress–strain curve**. A tough material is both strong and ductile.
- **Resilience** — elastic energy stored, \\(U_r = \sigma_y^2/2E\\).

## Hardness

Resistance to localized plastic deformation, measured by indentation (Brinell, Rockwell, Vickers). Hardness correlates with strength and wear resistance and is fast and non-destructive to measure.

## Fracture Toughness

Resistance to crack propagation, \\(K_{IC}\\):
\\[
K_I = Y\sigma\sqrt{\pi a},\qquad \text{failure when } K_I \ge K_{IC}.
\\]
A material can be strong yet have low fracture toughness (ceramics), failing catastrophically from small flaws. See [Failure Theories](../../eng/materials/failure.md).

## Time- and Cycle-Dependent Behavior

- **Fatigue** — failure under cyclic loading below the static strength (S–N curve, endurance limit).
- **Creep** — slow deformation under sustained load at high temperature, \\(\dot{\varepsilon} \propto \sigma^n e^{-Q/RT}\\).
- **Viscoelasticity** — rate-dependent response in polymers and tissues.

## The Strength–Toughness Tradeoff

Strengthening (harder, higher \\(\sigma_y\\)) usually reduces ductility and toughness. Material selection navigates this tradeoff using tools like **Ashby charts** (e.g. \\(E\\) vs. density, strength vs. toughness) to find the best material for a given performance index.

## See Also

- [Stress and Strain](../../eng/materials/stress-strain.md)
- [Failure Theories](../../eng/materials/failure.md)
- [Crystal Structures](crystals.md)
