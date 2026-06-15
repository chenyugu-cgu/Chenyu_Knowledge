# Feature Detection

**Features** are distinctive, repeatable points or regions in an image — corners, blobs, edges — that can be found again under viewpoint and lighting changes. They enable matching, tracking, stitching, and 3-D reconstruction.

## What Makes a Good Feature

- **Repeatable** — detected reliably across images.
- **Distinctive** — described uniquely enough to match.
- **Invariant** — robust to scale, rotation, illumination, and modest viewpoint change.

## Corner and Blob Detectors

- **Harris corner detector** — finds points where intensity changes in all directions (large eigenvalues of the structure tensor).
- **FAST** — very fast corner test, popular in real-time SLAM.
- **Blob detectors** (Laplacian/Difference of Gaussians) — find scale-localized regions.

## Descriptors

A **descriptor** encodes the appearance around a feature into a vector for matching:
- **SIFT** — scale- and rotation-invariant gradient histograms; robust, the classic benchmark.
- **SURF** — faster SIFT approximation.
- **ORB** — binary descriptor, fast and license-free; standard in real-time systems.

## Matching

Features are matched by nearest-neighbor in descriptor space, with the **ratio test** (Lowe) to reject ambiguous matches. **RANSAC** then fits a geometric model (homography, fundamental matrix) while discarding outliers — essential because matches are never perfect.

## Applications

- **Image stitching / panoramas** — match and warp overlapping images.
- **Object recognition** — match against templates.
- **Visual SLAM and odometry** — track features across frames to estimate motion. See [Localization and SLAM](../../app/robotics/slam.md).
- **3-D reconstruction** — correspondences across views give geometry. See [3D Vision](3d-vision.md).

## Learned Features

Deep networks now learn features end-to-end (see [Deep Learning for Vision](deep-vision.md)), often outperforming hand-crafted descriptors — though classical features remain valuable for geometry and low-compute settings.

## See Also

- [Image Processing](image-processing.md)
- [3D Vision](3d-vision.md)
- [Localization and SLAM](../../app/robotics/slam.md)
