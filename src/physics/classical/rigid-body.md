# Rigid-Body Dynamics

A **rigid body** has a fixed shape; its motion combines translation of the center of mass with rotation about it. Rigid-body dynamics governs spinning machinery, spacecraft attitude, and robot links.

## Rotational Quantities

Rotation is described by angular velocity \\(\boldsymbol{\omega}\\) and the **inertia tensor** \\(I\\), which relates angular momentum to angular velocity:
\\[
\mathbf{L} = I\boldsymbol{\omega}, \qquad
T_{\text{rot}} = \tfrac12\boldsymbol{\omega}^T I \boldsymbol{\omega}.
\\]
In 3-D, \\(I\\) is a \\(3\times3\\) symmetric tensor; its eigenvectors are the **principal axes**, along which \\(\mathbf{L}\\) and \\(\boldsymbol{\omega}\\) align.

## Euler's Equations

In the body frame aligned with the principal axes,
\\[
I_1\dot\omega_1 - (I_2 - I_3)\omega_2\omega_3 = \tau_1,
\\]
and cyclically. These nonlinear equations explain why free rotation about the intermediate axis is unstable (the "tennis-racket theorem").

## Gyroscopic Effects

A spinning body resists changes to its spin axis. An applied torque causes **precession** rather than tipping:
\\[
\boldsymbol{\tau} = \frac{d\mathbf{L}}{dt} = \boldsymbol{\Omega}_{\text{prec}}\times\mathbf{L}.
\\]
This underlies gyroscopes, the stability of bicycles and tops, and spacecraft attitude control.

## Orientation Representations

| Representation | Pros / cons |
|---|---|
| Euler angles | intuitive; suffer gimbal lock |
| Rotation matrix \\(R\in SO(3)\\) | no singularity; 9 redundant entries |
| Quaternions | compact, singularity-free; standard in robotics/graphics |

See [Robot Kinematics](../../app/robotics/kinematics.md) for the engineering use of these.

## Applications

Flywheels and rotors ([machine elements](../../eng/design/machine-elements.md)), spacecraft and drones, [vibration](../../eng/dynamics/vibrations.md) of rotating shafts, and every articulated [robot](../../app/robotics/dynamics.md).

## See Also

- [Newton's Laws](../../eng/dynamics/newton.md) — mass moment of inertia.
- [Robot Dynamics](../../app/robotics/dynamics.md)
- [Hamiltonian Mechanics](hamiltonian.md)
