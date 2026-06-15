# Dynamics

Robot dynamics relates joint torques to motion, accounting for inertia, gravity, and interaction forces. It is needed for accurate control, trajectory optimization, and simulation.

## The Equations of Motion

The dynamics of an \\(n\\)-DOF manipulator take the canonical form
\\[
M(\boldsymbol{\theta})\ddot{\boldsymbol{\theta}} + C(\boldsymbol{\theta},\dot{\boldsymbol{\theta}})\dot{\boldsymbol{\theta}} + \mathbf{g}(\boldsymbol{\theta}) = \boldsymbol{\tau},
\\]
where:
- \\(M\\) is the **inertia matrix** (symmetric, positive definite),
- \\(C\\) captures **Coriolis and centrifugal** effects,
- \\(\mathbf{g}\\) is the **gravity** torque vector,
- \\(\boldsymbol{\tau}\\) are the **joint torques**.

## Two Formulations

- **Lagrangian** — derive from energy: \\(\frac{d}{dt}\frac{\partial \mathcal{L}}{\partial \dot{\theta}} - \frac{\partial \mathcal{L}}{\partial \theta} = \tau\\), with \\(\mathcal{L} = T - V\\). Elegant and systematic.
- **Newton–Euler** — propagate velocities/accelerations outward and forces/torques inward link by link. Recursive and computationally efficient (\\(O(n)\\)) — preferred for real-time.

## Forward vs. Inverse Dynamics

| Problem | Given | Find | Use |
|---|---|---|---|
| **Inverse** | motion \\(\boldsymbol{\theta},\dot{\boldsymbol{\theta}},\ddot{\boldsymbol{\theta}}\\) | torques \\(\boldsymbol{\tau}\\) | control, planning |
| **Forward** | torques \\(\boldsymbol{\tau}\\) | motion \\(\ddot{\boldsymbol{\theta}}\\) | simulation |

## Computed-Torque Control

Because the model is known, we can **cancel** the nonlinear dynamics with feedforward and add linear feedback:
\\[
\boldsymbol{\tau} = M(\boldsymbol{\theta})\big(\ddot{\boldsymbol{\theta}}_d + K_d \dot{\mathbf{e}} + K_p \mathbf{e}\big) + C\dot{\boldsymbol{\theta}} + \mathbf{g}.
\\]
This linearizes the closed loop, giving uniform performance across the workspace — see [Robot Control](control.md).

## Contact and Floating-Base Dynamics

Legged robots and manipulators in contact add constraint forces (via Lagrange multipliers) and a floating base, leading to the constrained dynamics solved in modern whole-body controllers and MPC.

## See Also

- [Newton's Laws](../../eng/dynamics/newton.md)
- [Work and Energy](../../eng/dynamics/energy.md) — the Lagrangian.
- [Robot Control](control.md)
