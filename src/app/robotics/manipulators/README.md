# Manipulator Robotics

A robot manipulator is a chain of rigid links joined by actuated joints, ending in a tool. Making it useful takes a precise mathematical description of the arm. Kinematics says where the tool is for given joint angles and which joint angles reach a desired pose. The Jacobian tells how joint velocities and torques map to tool velocities and forces. Dynamics gives the torques needed to move. Control makes the arm follow a trajectory or press with a desired force.

This subsection follows the graduate course *Robotics* (Georgia Tech ME 6407), built on Craig's *Introduction to Robotics: Mechanics and Control*. Its later chapters go beyond the textbook into redundancy, haptics and teleoperation, and parallel robots.

## Chapters

**Kinematics**
1. [Spatial Descriptions and Transformations](spatial-descriptions.md)
2. [Forward Kinematics and the Denavit–Hartenberg Convention](forward-kinematics.md)
3. [Inverse Kinematics](inverse-kinematics.md)
4. [Jacobians, Singularities and Statics](jacobians-statics.md)
5. [Trajectory Generation](trajectory.md)

**Dynamics and control**
6. [Manipulator Dynamics](dynamics.md)
7. [Actuation, Transmissions and Redundancy](actuation.md)
8. [Manipulator Control](control.md)
9. [Force Control, Haptics and Teleoperation](force-control.md)

**Other architectures**
10. [Parallel Robots](parallel-robots.md)

## The Standard Pipeline

1. Assign link frames (DH parameters) and build the forward kinematics \\(T(q)\\).
2. Invert it for the joint angles that reach a goal pose, choosing among multiple solutions.
3. Plan a smooth joint-space or Cartesian trajectory through via points.
4. Compute the torques from the dynamics \\(M(q)\ddot q + C(q,\dot q)\dot q + G(q) = \tau\\).
5. Close the loop with PD plus gravity compensation, computed torque, or Cartesian (Jacobian) control. Add force or impedance control when the tool touches the environment.

## Related Pages

- [Robotics overview](../README.md), [Kinematics](../kinematics.md), [Dynamics](../dynamics.md), [Robot Control](../control.md), [Manipulation and Grasping](../manipulation.md).
- [Control of Multi-Input Physical Systems](../../../eng/control/nonlinear/multi-input.md) for adaptive and sliding robot control.
- [Mobile Robotics](../mobile-robotics/README.md) for planar transforms and wheeled robots.
