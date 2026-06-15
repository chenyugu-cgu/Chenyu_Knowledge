# Strength of Materials

Strength of materials (mechanics of materials) bridges the gap between the external forces found in [statics](../statics/README.md) and the **internal stresses, strains, and deformations** they produce. Its purpose is design: choosing a material and cross-section so a part neither breaks nor deflects excessively.

## The Central Questions

For any loaded member we ask three things:

1. **Stress** — is the internal force per unit area below the material's strength?
2. **Deformation** — is the deflection or elongation within tolerance?
3. **Stability** — will it buckle or fail by some other mode before the stress limit?

## Key Relationships

The chain from load to deformation runs:
\\[
\text{Load} \longrightarrow \text{Internal force} \longrightarrow \text{Stress } \sigma \overset{\text{Hooke}}{\longrightarrow} \text{Strain } \varepsilon \longrightarrow \text{Deformation}.
\\]
The linchpin is **Hooke's law** \\(\sigma = E\varepsilon\\), valid in the elastic range.

## Chapter Map

- [Stress and Strain](stress-strain.md) — definitions, the tension test, Mohr's circle.
- [Elasticity](elasticity.md) — Hooke's law, elastic constants, generalized 3-D form.
- [Axial Loading](axial.md) — bars in tension/compression, thermal stress.
- [Torsion](torsion.md) — shafts under twisting.
- [Bending and Shear](bending.md) — the flexure formula and shear stress.
- [Deflection of Beams](deflection.md) — slope and deflection curves.
- [Failure Theories](failure.md) — yield/fracture criteria, fatigue, buckling.

## Factor of Safety

Designs are sized so the working stress stays below the limit by a **factor of safety**:
\\[
n = \frac{\sigma_{\text{fail}}}{\sigma_{\text{allow}}} > 1,
\\]
chosen from codes and uncertainty in loads, material, and analysis.
