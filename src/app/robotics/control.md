# Robot Control

Robot control turns desired motions into actuator commands, closing the loop on sensed state. It applies [control theory](../../eng/control/README.md) to the robot's [dynamics](dynamics.md).

## Joint-Space vs. Task-Space Control

- **Joint-space control** tracks a reference trajectory \\(\boldsymbol{\theta}_d(t)\\) per joint — simplest, used after IK.
- **Task-space (operational-space) control** tracks the end-effector pose directly in Cartesian coordinates, using the Jacobian to map forces/velocities.

## Independent-Joint PID

Each joint is controlled by a PID loop treating coupling as disturbance:
\\[
\tau_i = K_p e_i + K_i\!\int e_i\,dt + K_d \dot{e}_i.
\\]
Simple and common, but performance degrades at high speed where dynamic coupling matters. See [PID Control](../../eng/control/pid.md).

## Computed-Torque (Model-Based) Control

Cancel the nonlinear dynamics with the model and add linear feedback:
\\[
\boldsymbol{\tau} = M(\boldsymbol{\theta})\big(\ddot{\boldsymbol{\theta}}_d + K_d\dot{\mathbf{e}} + K_p\mathbf{e}\big) + C(\boldsymbol{\theta},\dot{\boldsymbol{\theta}})\dot{\boldsymbol{\theta}} + \mathbf{g}(\boldsymbol{\theta}).
\\]
The closed loop becomes \\(\ddot{\mathbf{e}} + K_d\dot{\mathbf{e}} + K_p\mathbf{e} = 0\\) — decoupled and uniform across the workspace.

## Force and Impedance Control

For contact tasks (assembly, polishing, human interaction), pure position control is dangerous. **Impedance/admittance control** regulates the *relationship* between motion and force, making the robot behave like a tunable spring–damper:
\\[
\mathbf{F} = M_d\ddot{\mathbf{x}} + B_d\dot{\mathbf{x}} + K_d\mathbf{x}.
\\]
**Hybrid force/position control** commands force in constrained directions and position in free ones.

## Advanced Approaches

- **Whole-body control** for humanoids and legged robots — solves a constrained QP each step balancing many tasks.
- **Model predictive control (MPC)** for legged locomotion and agile flight — see [Optimal Control](../../eng/control/optimal.md).
- **Learned control** — reinforcement learning policies for locomotion and manipulation, see [Reinforcement Learning](../../cs/ml/rl.md).

## See Also

- [PID Control](../../eng/control/pid.md)
- [Modern Control](../../eng/control/modern.md)
- [Dynamics](dynamics.md)
