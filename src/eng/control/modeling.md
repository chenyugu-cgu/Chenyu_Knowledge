# Modeling of Systems

Control design begins with a **model** — a set of differential equations relating inputs to outputs. Good control demands a model that is accurate enough to predict behavior yet simple enough to design against.

## Physical Modeling

Most engineering systems are modeled from first principles using element laws and conservation:

| Domain | Effort | Flow | Element laws |
|---|---|---|---|
| Mechanical (translational) | force \\(F\\) | velocity \\(v\\) | \\(F=m\dot v,\ F=kx,\ F=b v\\) |
| Electrical | voltage \\(V\\) | current \\(i\\) | \\(V=L\dot i,\ i=C\dot V,\ V=Ri\\) |
| Fluid | pressure \\(p\\) | flow \\(q\\) | resistance, capacitance, inertance |
| Thermal | temperature \\(T\\) | heat rate \\(q\\) | \\(q = \Delta T/R,\ q=C\dot T\\) |

These analogies let the same mathematics serve every domain.

## Example: Mass–Spring–Damper

Newton's law gives the canonical second-order system:
\\[
m\ddot{x} + b\dot{x} + k x = F(t).
\\]
Its transfer function (from force to position) is
\\[
G(s) = \frac{X(s)}{F(s)} = \frac{1}{m s^2 + b s + k}.
\\]

## Example: DC Motor

Combining the electrical loop and the mechanical load yields a coupled model linking applied voltage to shaft speed/angle — the workhorse example for position and speed control.

## Linearization

Real systems are nonlinear. Around an operating point \\(\mathbf{x}_0\\), a first-order Taylor expansion gives a linear model:
\\[
\dot{\mathbf{x}} \approx A(\mathbf{x}-\mathbf{x}_0) + B(\mathbf{u}-\mathbf{u}_0),
\quad A = \left.\frac{\partial f}{\partial \mathbf{x}}\right|_0, \quad B = \left.\frac{\partial f}{\partial \mathbf{u}}\right|_0.
\\]
This is why classical (linear) control works in practice: most systems are operated near a setpoint where the linear approximation holds.

## Standard Second-Order Form

Many systems reduce to
\\[
G(s) = \frac{\omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2},
\\]
characterized by the **natural frequency** \\(\omega_n\\) and **damping ratio** \\(\zeta\\). These two numbers predict overshoot, settling time, and resonance — the vocabulary of the rest of this section.

## See Also

- [Transfer Functions](transfer.md)
- [State-Space Representation](state-space.md)
- [Vibrations](../dynamics/vibrations.md)
