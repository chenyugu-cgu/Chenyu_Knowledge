# Kinematics

Robot kinematics studies motion geometry — how joint angles map to the position and orientation of the end effector — without regard to the forces involved.

## Rigid-Body Transformations

A pose combines rotation \\(R \in SO(3)\\) and translation \\(\mathbf{p}\\), packaged as a \\(4\times4\\) **homogeneous transformation**:
\\[
T = \begin{bmatrix} R & \mathbf{p} \\ \mathbf{0}^T & 1 \end{bmatrix} \in SE(3).
\\]
Transforms compose by multiplication: \\(T_{0}^{2} = T_{0}^{1} T_{1}^{2}\\). Orientation may also be represented by Euler angles, axis–angle, or **quaternions** (singularity-free, used in practice).

## Forward Kinematics

Given joint variables \\(\boldsymbol{\theta} = (\theta_1,\dots,\theta_n)\\), forward kinematics computes the end-effector pose by chaining link transforms, standardized by **Denavit–Hartenberg (DH)** parameters:
\\[
T_0^n(\boldsymbol{\theta}) = \prod_{i=1}^{n} T_{i-1}^{i}(\theta_i).
\\]
This is always well-defined and unique.

## Inverse Kinematics

Inverse kinematics (IK) finds joint angles that achieve a desired pose — the hard, practically essential direction. It may have:
- **No solution** (target outside the workspace),
- **Multiple solutions** (elbow-up vs. elbow-down),
- **Infinite solutions** (redundant arms, \\(n > 6\\)).

Solved **analytically** (closed form for simple geometries) or **numerically** via iteration on the Jacobian.

## The Jacobian

The **Jacobian** \\(J(\boldsymbol{\theta})\\) maps joint velocities to end-effector velocity (twist):
\\[
\dot{\mathbf{x}} = J(\boldsymbol{\theta})\,\dot{\boldsymbol{\theta}}.
\\]
It is central to velocity control, force mapping (\\(\boldsymbol{\tau} = J^T\mathbf{F}\\)), and numerical IK (\\(\dot{\boldsymbol{\theta}} = J^{-1}\dot{\mathbf{x}}\\), or the pseudoinverse \\(J^{+}\\) for redundant/non-square cases).

## Singularities

At a **singularity**, \\(J\\) loses rank: the arm cannot move instantaneously in some direction, and joint velocities blow up near it. Detected by \\(\det(J) = 0\\) (or small singular values). Avoiding singularities is a key planning concern.

## See Also

- [Vector Spaces](../../math/linear-algebra/vector-spaces.md)
- [Dynamics](dynamics.md)
- [Kinematics in Dynamics](../../eng/dynamics/kinematics.md)
