# Electrostatics

Electrostatics treats electric fields produced by **stationary** charges.

## Coulomb's Law and the Electric Field

The force between point charges and the field of a charge \\(q\\):
\\[
\mathbf{F} = \frac{1}{4\pi\varepsilon_0}\frac{q_1 q_2}{r^2}\hat{\mathbf{r}}, \qquad
\mathbf{E} = \frac{1}{4\pi\varepsilon_0}\frac{q}{r^2}\hat{\mathbf{r}}.
\\]
Fields superpose linearly.

## Gauss's Law

The electric flux through any closed surface equals the enclosed charge over \\(\varepsilon_0\\):
\\[
\oint_S \mathbf{E}\cdot d\mathbf{A} = \frac{Q_{\text{enc}}}{\varepsilon_0}, \qquad \nabla\cdot\mathbf{E} = \frac{\rho}{\varepsilon_0}.
\\]
For symmetric charge distributions (spherical, cylindrical, planar) Gauss's law gives the field in one line.

## Electric Potential

The field is the gradient of a scalar **potential**:
\\[
\mathbf{E} = -\nabla V, \qquad V(\mathbf{r}) = \frac{1}{4\pi\varepsilon_0}\frac{q}{r}.
\\]
Potential differences (voltages) are what we actually measure. In charge-free regions \\(V\\) satisfies **Laplace's equation** \\(\nabla^2 V = 0\\) — solved by the [PDE methods](../../math/diffeq/pdes.md) of separation of variables.

## Capacitance and Energy

A capacitor stores charge per volt, \\(C = Q/V\\), and energy
\\[
U = \tfrac12 C V^2 = \tfrac12\varepsilon_0\!\int |\mathbf{E}|^2\,dV.
\\]
Energy resides in the field itself.

## Dielectrics

Insulating materials polarize in a field, increasing capacitance by the relative permittivity \\(\varepsilon_r\\). This governs capacitor design, insulation, and the dielectric properties of biological tissue (relevant to bioimpedance and [bioinstrumentation](../../app/biomed/instrumentation.md)).

## See Also

- [Magnetostatics](magnetostatics.md)
- [Circuit Laws](../../eng/electrical/circuits.md)
- [Vector Calculus](../../math/calculus/vector.md)
