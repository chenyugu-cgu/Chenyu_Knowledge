# Elasticity

Elasticity describes how a material deforms reversibly under load and springs back when unloaded. In the linear regime it is governed by **Hooke's law**.

## Hooke's Law

For uniaxial loading,
\\[
\sigma = E\,\varepsilon,
\\]
where \\(E\\) is **Young's modulus** (stiffness in tension/compression). For shear,
\\[
\tau = G\,\gamma,
\\]
with \\(G\\) the **shear modulus**.

## Elastic Constants

- **Young's modulus** \\(E\\): axial stiffness.
- **Poisson's ratio** \\(\nu\\): lateral contraction per axial extension, \\(\nu = -\varepsilon_{\text{lat}}/\varepsilon_{\text{axial}}\\) (typically 0.25–0.35).
- **Shear modulus** \\(G\\): \\(G = \dfrac{E}{2(1+\nu)}\\).
- **Bulk modulus** \\(K\\): resistance to volume change, \\(K = \dfrac{E}{3(1-2\nu)}\\).

For an **isotropic** material only two of these are independent.

## Generalized 3-D Hooke's Law

In three dimensions, normal strains couple through Poisson's ratio:
\\[
\varepsilon_x = \frac{1}{E}\big[\sigma_x - \nu(\sigma_y + \sigma_z)\big],
\\]
and cyclically for \\(\varepsilon_y, \varepsilon_z\\), with shear relations \\(\gamma_{xy} = \tau_{xy}/G\\). In matrix form \\(\boldsymbol{\varepsilon} = \mathbf{S}\boldsymbol{\sigma}\\), where \\(\mathbf{S}\\) is the compliance matrix and \\(\mathbf{C}=\mathbf{S}^{-1}\\) the stiffness matrix.

## Strain Energy

The energy stored per unit volume in elastic deformation is
\\[
u = \tfrac{1}{2}\sigma\varepsilon = \frac{\sigma^2}{2E}.
\\]
This **strain energy** underlies energy methods (Castigliano's theorem) for computing deflections — see [Deflection of Beams](deflection.md).

## Anisotropy

Real materials are not always isotropic:
- **Orthotropic** (wood, fiber composites): different properties along three axes.
- **Anisotropic** (single crystals): full stiffness tensor with up to 21 independent constants.

Composite design exploits anisotropy deliberately; see [Polymers and Composites](../../app/materials-science/polymers.md).

## Typical Values

| Material | \\(E\\) (GPa) | \\(\nu\\) |
|---|---|---|
| Steel | 200 | 0.30 |
| Aluminum | 69 | 0.33 |
| Concrete | 30 | 0.20 |
| Rubber | 0.01–0.1 | ~0.5 |

## See Also

- [Stress and Strain](stress-strain.md)
- [Axial Loading](axial.md)
