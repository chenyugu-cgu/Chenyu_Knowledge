# Conservation Laws

Fluid dynamics rests on three conservation principles — mass, momentum, and energy — applied to a **control volume** (a fixed region of space) via the Reynolds transport theorem.

## Conservation of Mass (Continuity)

Mass is neither created nor destroyed. For steady flow through a stream tube,
\\[
\dot{m} = \rho_1 A_1 V_1 = \rho_2 A_2 V_2.
\\]
For incompressible flow, \\(A_1 V_1 = A_2 V_2\\): a narrowing pipe speeds the flow. In differential form,
\\[
\frac{\partial \rho}{\partial t} + \nabla\cdot(\rho \mathbf{V}) = 0.
\\]

## Conservation of Momentum

Newton's second law for a control volume relates the net force to the momentum flux:
\\[
\sum \mathbf{F} = \frac{d}{dt}\int_{CV}\rho\mathbf{V}\,dV + \int_{CS}\rho\mathbf{V}(\mathbf{V}\cdot\mathbf{n})\,dA.
\\]
This computes thrust on pipe bends, jet forces, and rocket/propulsion forces.

## The Bernoulli Equation

Along a streamline for steady, incompressible, inviscid flow, mechanical energy is conserved:
\\[
p + \tfrac{1}{2}\rho V^2 + \rho g z = \text{const}.
\\]
The three terms are static, dynamic, and hydrostatic pressure. Bernoulli explains lift, venturi meters, pitot tubes, and the drop in pressure where flow speeds up.

### Worked Example: Pitot Tube

A pitot tube measures airspeed from the difference between stagnation and static pressure:
\\[
V = \sqrt{\frac{2(p_0 - p)}{\rho}}.
\\]

## Conservation of Energy

The steady-flow energy equation extends Bernoulli to include pump work, turbine work, and friction losses (the head form):
\\[
\frac{p_1}{\gamma} + \frac{V_1^2}{2g} + z_1 + h_{\text{pump}} = \frac{p_2}{\gamma} + \frac{V_2^2}{2g} + z_2 + h_{\text{turbine}} + h_{\text{loss}}.
\\]

## The Navier–Stokes Equations

The full governing equations for a viscous, incompressible Newtonian fluid:
\\[
\rho\left(\frac{\partial \mathbf{V}}{\partial t} + \mathbf{V}\cdot\nabla\mathbf{V}\right) = -\nabla p + \mu\nabla^2\mathbf{V} + \rho\mathbf{g}.
\\]
Analytic solutions exist only for simple geometries; most real flows are solved numerically (CFD) — see [Partial Differential Equations](../../math/numerical/pdes.md). Their well-posedness in 3-D remains a Millennium Prize problem.

## See Also

- [Bernoulli and pipe flow → Internal Flows](internal.md)
- [Vector Calculus](../../math/calculus/vector.md)
