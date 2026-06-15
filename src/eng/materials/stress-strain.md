# Stress and Strain

## Stress

**Stress** is internal force per unit area. The two basic kinds are normal and shear:
\\[
\sigma = \frac{N}{A} \quad(\text{normal}), \qquad \tau = \frac{V}{A} \quad(\text{shear}).
\\]
Normal stress acts perpendicular to a surface (tension positive, compression negative); shear stress acts parallel to it. Units are pascals (Pa = N/m²) or psi.

## Strain

**Strain** is the dimensionless measure of deformation:
\\[
\varepsilon = \frac{\Delta L}{L_0} \quad(\text{normal strain}), \qquad
\gamma = \frac{\Delta x}{h} \quad(\text{shear strain, the change in angle}).
\\]

## The Tension Test

Pulling a standardized specimen gives the **stress–strain curve**, the fingerprint of a material:

- **Proportional/elastic region** — linear; slope is Young's modulus \\(E\\). Unloading returns to zero strain.
- **Yield point** \\(\sigma_y\\) — onset of permanent (plastic) deformation; often defined by the 0.2% offset.
- **Strain hardening** — stress rises with continued strain to the **ultimate tensile strength** \\(\sigma_u\\).
- **Necking and fracture** — localized thinning to rupture at \\(\sigma_f\\).

**Ductile** materials (mild steel) show large plastic strain before fracture; **brittle** materials (cast iron, ceramics) fracture with little warning.

## Plane Stress and Stress Transformation

At a point, the stress on a plane rotated by \\(\theta\\) is
\\[
\sigma_{\theta} = \frac{\sigma_x + \sigma_y}{2} + \frac{\sigma_x - \sigma_y}{2}\cos 2\theta + \tau_{xy}\sin 2\theta,
\\]
\\[
\tau_{\theta} = -\frac{\sigma_x - \sigma_y}{2}\sin 2\theta + \tau_{xy}\cos 2\theta.
\\]
The **principal stresses** (where \\(\tau=0\\)) are
\\[
\sigma_{1,2} = \frac{\sigma_x + \sigma_y}{2} \pm \sqrt{\left(\frac{\sigma_x - \sigma_y}{2}\right)^2 + \tau_{xy}^2}.
\\]

## Mohr's Circle

Plotting \\((\sigma,\tau)\\) traces a circle of center \\(\left(\tfrac{\sigma_x+\sigma_y}{2},0\right)\\) and radius \\(R=\sqrt{\left(\tfrac{\sigma_x-\sigma_y}{2}\right)^2+\tau_{xy}^2}\\). It reads off principal stresses (circle's horizontal extremes) and the maximum shear stress \\(\tau_{\max}=R\\) graphically — indispensable for failure analysis.

## See Also

- [Elasticity](elasticity.md)
- [Failure Theories](failure.md)
