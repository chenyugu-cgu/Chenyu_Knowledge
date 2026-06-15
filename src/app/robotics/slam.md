# Localization and SLAM

To act in the world a robot must know **where it is** (localization) and often **what the world looks like** (mapping). Doing both at once — **Simultaneous Localization and Mapping (SLAM)** — is a defining problem of mobile robotics.

## Localization

Given a map, estimate the robot's pose from sensor data. This is a [state-estimation](sensing.md) problem solved by Bayesian filters:
- **Kalman / Extended Kalman Filter** — for Gaussian, (near-)linear models.
- **Particle filter (Monte Carlo Localization)** — represents arbitrary, multimodal beliefs with sampled particles; robust to the "kidnapped robot" problem.

The recursive Bayes update: predict with the motion model, correct with the measurement model.

## The SLAM Problem

Without a prior map, the robot must build one **while** localizing in it — a chicken-and-egg coupling, since pose errors corrupt the map and map errors corrupt the pose. SLAM jointly estimates the trajectory and map and is **probabilistically** formulated over both.

## Approaches

| Approach | Idea |
|---|---|
| EKF-SLAM | joint Gaussian over pose + landmarks (scales poorly) |
| FastSLAM | particle filter + per-landmark EKFs |
| **Graph-based SLAM** | poses/landmarks as nodes, constraints as edges; optimize the graph |

Modern systems are **graph-based**: build a pose graph from odometry and sensor constraints, then solve a large sparse nonlinear least-squares problem (bundle adjustment) — see [Scientific Computing](../../cs/scientific-computing/linear-systems.md).

## Loop Closure

Recognizing a previously visited place adds a powerful constraint that corrects accumulated **drift**. Place recognition (often via [visual features](../../cs/vision/features.md) or learned descriptors) is what keeps long-term maps consistent.

## Sensors for SLAM

- **Visual SLAM** — cameras + [feature tracking](../../cs/vision/3d-vision.md) (ORB-SLAM).
- **Lidar SLAM** — point-cloud registration (ICP), robust geometry.
- **Visual-inertial** — fuse camera with IMU for scale and robustness.

## Applications

Self-driving cars, drones, warehouse robots, AR/VR headsets, and planetary rovers.

## See Also

- [Sensing and Perception](sensing.md)
- [3D Vision](../../cs/vision/3d-vision.md)
- [Bayesian Inference](../../math/probability/bayes.md)
