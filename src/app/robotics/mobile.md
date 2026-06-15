# Mobile Robots and Locomotion

Mobile robots move through the world — wheeled, tracked, legged, flying, or swimming. Locomotion adds the challenge of moving the whole platform, not just an arm.

## Wheeled Robots and Nonholonomic Constraints

The common **differential-drive** robot is controlled by two wheel speeds, with kinematics
\\[
\dot{x} = v\cos\theta, \quad \dot{y} = v\sin\theta, \quad \dot{\theta} = \omega.
\\]
It is **nonholonomic**: it cannot move sideways instantaneously (like a car). This constraint complicates [path planning](planning.md) and parking-like maneuvers. Other configurations: Ackermann steering (cars), omnidirectional (mecanum) wheels, and skid-steer.

## Legged Locomotion

Legs traverse rough terrain wheels cannot, but balance is hard. Key concepts:
- **Static stability** — center of mass stays over the support polygon (slow, always stable).
- **Dynamic stability** — the **Zero-Moment Point (ZMP)** stays within the support; enables fast walking/running.
- **Gaits** — coordinated leg patterns (walk, trot, gallop).

Modern legged robots use [model predictive control](../../eng/control/optimal.md) and increasingly [reinforcement learning](../../cs/ml/rl.md) for robust locomotion.

## Aerial and Underwater Robots

- **Quadrotors** — underactuated (4 motors, 6 DOF); control thrust + attitude to translate. Agile but inherently unstable, needing fast feedback.
- **Fixed-wing** — efficient long-range flight, aerodynamics-limited.
- **Underwater (AUVs)** — buoyancy, drag, and limited communication dominate.

## Navigation Stack

A mobile robot integrates: [localization/SLAM](slam.md) → global [path planning](planning.md) → local obstacle avoidance → motion [control](control.md), running continuously as the world changes.

## Energy and Autonomy

Battery energy density limits range and endurance; efficient gaits and trajectory optimization extend it — a key real-world constraint.

## See Also

- [Motion Planning](planning.md)
- [Localization and SLAM](slam.md)
- [Robot Control](control.md)
