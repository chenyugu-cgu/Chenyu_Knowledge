# Central-Force Motion

A **central force** points along the line to a fixed center with magnitude depending only on distance, \\(\mathbf{F} = f(r)\hat{\mathbf{r}}\\). Gravity and the Coulomb force are central; their analysis explains planetary orbits and atomic models.

## Conservation Laws

Central forces conserve **angular momentum** (the torque about the center is zero):
\\[
L = m r^2 \dot\theta = \text{const}.
\\]
This immediately gives **Kepler's second law** — equal areas swept in equal times. Energy is also conserved for conservative central forces.

## Reduction to One Dimension

Using angular-momentum conservation, the radial motion separates with an **effective potential**:
\\[
\tfrac12 m\dot{r}^2 + \underbrace{\left[V(r) + \frac{L^2}{2mr^2}\right]}_{V_{\text{eff}}(r)} = E.
\\]
The centrifugal term \\(L^2/2mr^2\\) acts as a repulsive barrier; minima of \\(V_{\text{eff}}\\) give circular orbits.

## The Kepler Problem

For an inverse-square force \\(V = -k/r\\), the orbits are **conic sections**:
\\[
r(\theta) = \frac{p}{1 + e\cos\theta},
\\]
with eccentricity \\(e\\) selecting ellipse (\\(e<1\\), bound), parabola (\\(e=1\\)), or hyperbola (\\(e>1\\)). This yields all three of **Kepler's laws**, including \\(T^2 \propto a^3\\).

## Applications

- **Orbital mechanics** — satellites, transfer orbits, escape velocity \\(v_{esc} = \sqrt{2GM/r}\\).
- **Atomic physics** — the classical hydrogen atom (refined by [quantum mechanics](../modern/quantum.md)).
- **Scattering** — Rutherford scattering from the Coulomb potential.

## See Also

- [Newton's Laws](../../eng/dynamics/newton.md)
- [Lagrangian Mechanics](lagrangian.md)
- [Impulse and Momentum](../../eng/dynamics/momentum.md)
