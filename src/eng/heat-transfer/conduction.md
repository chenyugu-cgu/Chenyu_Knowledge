# Conduction

Conduction transfers heat through a material by molecular and electron interaction, without bulk motion. It dominates in solids.

## Fourier's Law

Heat flux is proportional to the temperature gradient:
\\[
q = -k A\frac{dT}{dx},
\\]
where \\(k\\) is the **thermal conductivity** (W/m·K). Metals conduct well (Cu ~400, steel ~50); insulators poorly (foam ~0.03). The minus sign encodes flow from hot to cold.

## The Heat Equation

Energy conservation gives the transient conduction PDE:
\\[
\frac{\partial T}{\partial t} = \alpha\nabla^2 T, \qquad \alpha = \frac{k}{\rho c_p},
\\]
with **thermal diffusivity** \\(\alpha\\) setting how fast temperature changes propagate. Steady state reduces to Laplace's equation \\(\nabla^2 T = 0\\) — solved by the [PDE methods](../../math/diffeq/pdes.md) of separation of variables.

## Thermal Resistance

For 1-D steady conduction, \\(R = L/kA\\). Composite walls add resistances in series:
\\[
q = \frac{\Delta T}{\sum R_i}.
\\]
Radial conduction through a pipe wall uses \\(R = \ln(r_o/r_i)/(2\pi k L)\\).

## Extended Surfaces (Fins)

Fins increase surface area to boost heat removal. A fin's temperature obeys
\\[
\frac{d^2\theta}{dx^2} - m^2\theta = 0, \quad m = \sqrt{\frac{hP}{kA_c}},
\\]
giving exponential/hyperbolic profiles and a **fin efficiency** — the basis of heat sinks for electronics and engines.

## Transient Conduction

The **Biot number** \\(Bi = hL/k\\) decides the approach: \\(Bi < 0.1\\) allows the **lumped-capacitance** model (uniform \\(T\\), exponential cooling \\(T(t) = T_\infty + (T_0-T_\infty)e^{-t/\tau}\\)); otherwise spatial gradients matter and the full heat equation is needed.

## See Also

- [Convection](convection.md)
- [Partial Differential Equations](../../math/diffeq/pdes.md)
- [Circuit Laws](../electrical/circuits.md) — the resistance analogy.
