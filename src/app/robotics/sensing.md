# Sensing and Perception

A robot acts on its **belief** about the world, built from noisy, partial sensor data. Perception turns raw measurements into usable state estimates.

## Sensors

| Sensor | Measures |
|---|---|
| Encoders | joint angles/velocities |
| IMU (accelerometer + gyro) | acceleration, angular rate |
| Cameras | images (color, depth) |
| Lidar | range/point clouds |
| Force/torque | contact forces |
| GPS | global position (outdoors) |

No single sensor is sufficient; robust perception **fuses** them.

## State Estimation and the Kalman Filter

The **Kalman filter** optimally fuses a motion model with measurements for linear-Gaussian systems, alternating predict and update:
\\[
\hat{\mathbf{x}}_k^- = A\hat{\mathbf{x}}_{k-1} + B\mathbf{u}_k, \qquad
\hat{\mathbf{x}}_k = \hat{\mathbf{x}}_k^- + K_k(\mathbf{z}_k - H\hat{\mathbf{x}}_k^-),
\\]
with Kalman gain \\(K_k\\) balancing model vs. measurement trust. The **Extended/Unscented KF** and **particle filters** handle nonlinear and non-Gaussian cases. This is the estimation dual of [Optimal Control](../../eng/control/optimal.md).

## Computer Vision

- **Feature detection/matching** (SIFT, ORB) for tracking and registration.
- **Deep learning** for detection, segmentation, and pose estimation — see [Deep Learning](../../cs/ml/deep-learning.md).
- **Stereo/depth** and structure-from-motion recover 3-D geometry.

## SLAM

**Simultaneous Localization and Mapping** builds a map of an unknown environment while tracking the robot within it — a chicken-and-egg problem solved with filtering (EKF-SLAM) or graph optimization (pose-graph / bundle adjustment). It underlies autonomous navigation, AR, and self-driving.

## Sensor Fusion in Practice

Complementary filters blend high-rate IMU with drift-free vision/GPS. The guiding principle: combine sources so each covers the others' weaknesses (IMU is fast but drifts; vision is accurate but slow).

## See Also

- [Bayesian Inference](../../math/probability/bayes.md)
- [Motion Planning](planning.md)
- [Signal Processing](../../eng/electrical/signal-processing.md)
