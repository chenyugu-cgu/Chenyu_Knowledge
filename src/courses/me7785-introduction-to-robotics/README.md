# Mobile Robotics

A mobile robot has to answer three questions continuously: *where am I*, *where am I going*, and *how do I get there*. This subsection builds the tools a ground robot needs to answer them. Coordinate transforms and kinematics describe motion. Feedback and behavior-based control steer the robot. Images and internal sensors give it information about the world. Probabilistic filters turn noisy measurements into a belief about its state, and planners search for a path through the space of configurations.

The subsection follows the graduate course *Introduction to Robotics* (Georgia Tech ME 7785), a hands-on course built around a differential-drive robot running ROS.

## Chapters

**Motion and control**
1. [Coordinate Transforms and Differential-Drive Kinematics](transforms-kinematics.md)
2. [Feedback Control for Mobile Robots](feedback-control.md)
3. [Behavior-Based Control: Go-to-Goal, Obstacle Avoidance and Switching](behavior-control.md)

**Perception and software**
4. [Image Processing for Robots](robot-vision.md)
5. [ROS and Linux for Robotics](ros.md)
6. [Internal Sensors and Odometry](sensors.md)

**Estimation**
7. [Bayesian State Estimation](bayes-filters.md)
8. [Particle Filters and Monte Carlo Localization](particle-filters.md)
9. [Kalman and Extended Kalman Filters for Robots](kalman-filters.md)

**Planning and learning**
10. [Configuration Space and Path Planning](path-planning.md)
11. [Introduction to Machine Learning for Robotics](learning.md)

## The Sense–Plan–Act Loop

| Stage | Question | Tools in this subsection |
|---|---|---|
| Sense | What do the sensors say? | Encoders, IMU, camera; filtering, thresholding, RANSAC |
| Estimate | Where am I? | Bayes, particle and Kalman filters |
| Plan | Where should I go? | C-space, roadmaps, A* and other graph searches |
| Act | How do I get there? | Kinematics, PID, go-to-goal and obstacle-avoidance behaviors |

## Related Pages

- Robotics overview, Mobile Robots and Locomotion, Localization and SLAM, Motion Planning.
- [Linear Systems Theory](../me6401-linear-control/README.md) for the theory behind Kalman filtering and feedback.
- Computer Vision for deeper image processing.
