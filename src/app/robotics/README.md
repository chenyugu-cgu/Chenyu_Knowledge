# Robotics

Robotics integrates mechanics, control, sensing, and computation to build machines that perceive and act in the physical world. It is the meeting point of nearly every other section of this book.

## The Sense–Plan–Act Loop

A robot continually:
1. **Senses** its state and environment (encoders, cameras, IMUs, lidar) — see [Sensing and Perception](sensing.md).
2. **Plans** what to do (paths, trajectories, decisions) — see [Motion Planning](planning.md).
3. **Acts** through controlled actuators — see [Robot Control](control.md).

Underlying it all are **kinematics** (geometry of motion) and **dynamics** (forces and torques).

## Configuration Space

A robot's state is a point in **configuration space** \\(\mathcal{C}\\), with dimension equal to the **degrees of freedom (DOF)**. A 6-DOF arm needs six joint values to fully specify its pose; planning happens in this space, not the workspace.

## Chapter Map

- [Kinematics](kinematics.md) — forward/inverse kinematics, transformations.
- [Dynamics](dynamics.md) — equations of motion, torques.
- [Motion Planning](planning.md) — paths and trajectories.
- [Sensing and Perception](sensing.md) — state estimation, vision, SLAM.
- [Robot Control](control.md) — joint and task-space control.
- [Localization and SLAM](slam.md) — knowing where you are while mapping.
- [Mobile Robots and Locomotion](mobile.md) — wheeled, legged, aerial.
- [Manipulation and Grasping](manipulation.md) — physical interaction with objects.
- [Human-Robot Interaction](hri.md) — safe, collaborative operation.

## Foundations Used Here

Robotics draws on [Linear Algebra](../../math/linear-algebra/README.md) (transforms), [Dynamics](../../eng/dynamics/README.md) (Newton–Euler, Lagrange), [Control Systems](../../eng/control/README.md) (feedback), and [Machine Learning](../../cs/ml/README.md) (perception, learned policies).
