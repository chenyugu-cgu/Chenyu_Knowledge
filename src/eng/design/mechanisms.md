# Mechanisms and Linkages

A **mechanism** is an assembly of rigid links and joints that transforms motion and force — converting rotation to translation, amplifying displacement, or tracing a path. Mechanism design (kinematics of machinery) is the geometry of moving machines.

## Mobility (Degrees of Freedom)

The number of independent inputs is given by **Gruebler's/Kutzbach's equation** for planar mechanisms:
\\[
M = 3(n - 1) - 2 j_1 - j_2,
\\]
where \\(n\\) is links, \\(j_1\\) full (1-DOF) joints, \\(j_2\\) half joints. \\(M=1\\) means one motor fully drives the mechanism.

## The Four-Bar Linkage

The workhorse planar mechanism. **Grashof's criterion** predicts whether a link can fully rotate: if \\(s + l \le p + q\\) (shortest + longest ≤ other two), at least one link makes a full revolution (crank-rocker, double-crank). Four-bars generate complex paths from a single rotation.

## Common Mechanisms

| Mechanism | Function |
|---|---|
| Slider-crank | rotation ↔ translation (engines, pumps) |
| Cam-follower | arbitrary motion profile from a rotating cam |
| Gear train | speed/torque ratio (see [Power Transmission](power-transmission.md)) |
| Ratchet | one-way motion |
| Geneva drive | intermittent indexing |

## Kinematic Analysis

Position, velocity, and acceleration of any point are found by vector-loop equations (closure), differentiated in time. The **velocity ratio** and **mechanical advantage** follow from the geometry — and the [Jacobian](../../app/robotics/kinematics.md) generalizes this to robots.

## Synthesis

The inverse problem: design a mechanism to achieve a specified motion, path, or function generation. Graphical and analytical synthesis methods place pivots to hit target positions.

## See Also

- [Robot Kinematics](../../app/robotics/kinematics.md)
- [Power Transmission](power-transmission.md)
- [Kinematics](../dynamics/kinematics.md)
