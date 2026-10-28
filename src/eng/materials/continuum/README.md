# Continuum Mechanics

Strength of materials treats a beam or a bar as a one-dimensional object and asks how it bends or breaks. Continuum mechanics asks the more general question for any body: how do points of a deforming medium move, what forces act inside it, and which relations between stress and deformation describe a given material? The answers apply equally to a steel beam, a rubber balloon, a flowing fluid and a seismic wave.

This subsection follows the graduate course *Continuum Mechanics* (Georgia Tech ME 6201, Fall 2024). The course builds the theory in a fixed order. It starts with tensor algebra and calculus, then describes deformation (kinematics) and the conservation laws that govern it (kinetics). Constitutive theory restricts what a particular material can do, and the remaining chapters apply that theory to viscous fluids, hyperelastic solids, linear elastic solids and elastic waves.

## Chapters

**Mathematical foundations**
1. [Tensor Algebra and Calculus](tensors.md)
2. [Kinematics of Deformation](kinematics.md)

**Balance laws**
3. [Balance Laws and Stress](balance-laws.md)

**Constitutive theory**
4. [Constitutive Theory and Material Symmetry](constitutive.md)

**Applications**
5. [Viscous Fluids](fluids.md)
6. [Hyperelastic Solids](hyperelasticity.md)
7. [Linear Elasticity](linear-elasticity.md)
8. [Elastic Waves and Impact](waves.md)

## Notation

The course uses index notation with the summation convention, so \\(\sigma\_{ij} n\_j\\) means \\(\sum\_j \sigma\_{ij} n\_j\\). Vectors and tensors are written in boldface where the distinction matters. Capital letters refer to the reference configuration and lowercase letters to the current configuration. The deformation gradient is \\(\mathbf F = \partial \mathbf x / \partial \mathbf X\\), and \\(J = \det \mathbf F\\) measures local volume change.

## Related Pages

- [Stress and Strain](../stress-strain.md) and [Elasticity](../elasticity.md) for the one-dimensional and beam-level version of this material.
- [Fluid Mechanics](../../fluid/README.md) for the engineering treatment of fluid flow.
- [Eigenvalues and Eigenvectors](../../../math/linear-algebra/eigen.md) and [Partial Differential Equations](../../../math/diffeq/pdes.md) for the mathematical background.
