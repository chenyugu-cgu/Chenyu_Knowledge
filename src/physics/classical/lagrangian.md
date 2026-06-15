# Lagrangian Mechanics

Lagrangian mechanics reformulates dynamics in terms of **energy** and **generalized coordinates** rather than forces and vectors. It automatically handles constraints and is the systematic way to derive equations of motion for complex systems.

## The Lagrangian

Define the **Lagrangian** as kinetic minus potential energy:
\\[
L(q, \dot{q}, t) = T - V,
\\]
expressed in **generalized coordinates** \\(q_i\\) (any convenient set — angles, distances — that describe the configuration).

## The Euler–Lagrange Equations

The motion extremizes the **action** \\(S = \int L\,dt\\) (the principle of least action). This yields, for each coordinate,
\\[
\frac{d}{dt}\!\left(\frac{\partial L}{\partial \dot{q}_i}\right) - \frac{\partial L}{\partial q_i} = Q_i,
\\]
where \\(Q_i\\) is any non-conservative generalized force (friction, applied torque). One scalar function \\(L\\) generates all the equations of motion — no free-body diagrams.

## Worked Example: Simple Pendulum

With angle \\(\theta\\), length \\(\ell\\): \\(T = \tfrac12 m\ell^2\dot\theta^2\\), \\(V = -mg\ell\cos\theta\\). Then
\\[
\frac{d}{dt}(m\ell^2\dot\theta) + mg\ell\sin\theta = 0 \;\Rightarrow\; \ddot\theta + \frac{g}{\ell}\sin\theta = 0.
\\]
No tension force ever appears — the constraint is built into the coordinate.

## Constraints and Generalized Coordinates

By choosing coordinates that satisfy the constraints automatically (e.g. \\(\theta\\) for a pendulum), constraint forces drop out. Holonomic constraints reduce the number of coordinates; Lagrange multipliers handle the rest.

## Why Robotics Loves It

For an \\(n\\)-link manipulator, the Lagrangian directly produces the canonical form
\\[
M(q)\ddot{q} + C(q,\dot{q})\dot{q} + g(q) = \tau,
\\]
the equations used for [robot dynamics](../../app/robotics/dynamics.md) and computed-torque control.

## See Also

- [Hamiltonian Mechanics](hamiltonian.md)
- [Robot Dynamics](../../app/robotics/dynamics.md)
- [Calculus of Variations → Optimal Control](../../eng/control/optimal.md)
