# Classical Mechanics

Classical mechanics is the physics of motion at everyday scales. Beyond the Newtonian \\(\mathbf{F}=m\mathbf{a}\\) of the [Dynamics](../../eng/dynamics/README.md) chapter, this section develops the **analytical mechanics** of Lagrange and Hamilton — reformulations that handle constraints elegantly and underpin robotics, control, and quantum mechanics.

## Three Equivalent Formulations

| Formulation | Central object | Strength |
|---|---|---|
| Newtonian | force \\(\mathbf{F}\\), vectors | intuitive, direct |
| Lagrangian | energy \\(L = T - V\\) | constraints, generalized coordinates |
| Hamiltonian | energy \\(H = T + V\\), phase space | conservation laws, quantum bridge |

All three describe the same physics; the right choice makes a given problem tractable.

## Why It Matters for Engineering

- **Robotics** — the manipulator equations of motion come from the Lagrangian. See [Robot Dynamics](../../app/robotics/dynamics.md).
- **Control** — Hamiltonian methods appear in [optimal control](../../eng/control/optimal.md) (Pontryagin's principle).
- **Multibody systems** — generalized coordinates tame complex linkages.

## Chapter Map

- [Lagrangian Mechanics](lagrangian.md)
- [Hamiltonian Mechanics](hamiltonian.md)
- [Central-Force Motion](central-force.md)
- [Rigid-Body Dynamics](rigid-body.md)

## See Also

- [Newton's Laws](../../eng/dynamics/newton.md)
- [Work and Energy](../../eng/dynamics/energy.md)
