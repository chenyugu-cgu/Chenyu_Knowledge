# 3D Vision

3-D vision recovers the geometry of a scene from images — depth, shape, and camera motion. It is the perceptual core of robotics, AR/VR, and autonomous navigation.

## The Camera Model

A **pinhole camera** projects a 3-D point onto the image plane via the intrinsic matrix \\(K\\) and the camera pose \\([R\,|\,\mathbf{t}]\\):
\\[
\mathbf{x} \sim K\,[R\,|\,\mathbf{t}]\,\mathbf{X}.
\\]
**Calibration** estimates \\(K\\) and lens distortion — the prerequisite for any metric 3-D measurement.

## Stereo Vision

Two cameras a baseline \\(b\\) apart see a point at different image positions (**disparity** \\(d\\)). Depth follows from triangulation:
\\[
Z = \frac{f\,b}{d}.
\\]
Matching corresponding pixels (constrained to **epipolar lines** by the fundamental/essential matrix) yields a dense depth map.

## Structure from Motion (SfM)

From many images of a static scene (or a moving camera), SfM jointly recovers camera poses and a sparse 3-D point cloud by matching [features](features.md) and minimizing reprojection error (**bundle adjustment**). It is the offline cousin of [visual SLAM](../../app/robotics/slam.md).

## Depth Sensors

- **Structured light** (e.g. original Kinect) — project a known pattern, infer depth from its deformation.
- **Time-of-flight / lidar** — measure light travel time.
- **Learned monocular depth** — neural networks estimate depth from a single image.

## Point Clouds and Reconstruction

Depth data becomes a **point cloud**, registered across views (ICP — iterative closest point) and meshed into surfaces. Used in robotics mapping, 3-D scanning, and surgical navigation.

## Applications

Robot navigation and grasping ([Manipulation](../../app/robotics/manipulation.md)), autonomous driving, AR/VR, 3-D scanning, and image-guided surgery.

## See Also

- [Feature Detection](features.md)
- [Localization and SLAM](../../app/robotics/slam.md)
- [Sensing and Perception](../../app/robotics/sensing.md)
