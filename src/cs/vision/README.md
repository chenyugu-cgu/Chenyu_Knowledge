# Computer Vision

Computer vision extracts meaning from images and video — detecting objects, measuring scenes, reconstructing 3-D structure. It is essential to robotics, autonomous vehicles, and [medical imaging](../../app/biomed/imaging.md), and a flagship application of [deep learning](../ml/deep-learning.md).

## An Image Is Data

A grayscale image is a 2-D array of intensities; a color image has three channels. Vision treats images as signals (the 2-D extension of [signal processing](../../eng/electrical/signal-processing.md)) and as inputs to learned models.

## The Vision Pipeline

\\[
\text{image} \to \text{preprocessing} \to \text{features / representation} \to \text{interpretation (detect, classify, reconstruct)}.
\\]
Classical vision hand-crafts features; modern vision learns them with neural networks. Both remain useful.

## Chapter Map

- [Image Processing](image-processing.md) — filtering, edges, morphology.
- [Feature Detection](features.md) — corners, descriptors, matching.
- [Deep Learning for Vision](deep-vision.md) — CNNs, detection, segmentation.
- [3D Vision](3d-vision.md) — stereo, structure from motion, depth.

## Why It Matters Here

- **Robotics** — perception for navigation and [manipulation](../../app/robotics/manipulation.md), plus [SLAM](../../app/robotics/slam.md).
- **Biomedical** — analyzing X-ray, MRI, CT, and microscopy images ([Medical Imaging](../../app/biomed/imaging.md)).
- **Autonomous systems** — detecting and tracking the world.

## See Also

- [Signal Processing](../../eng/electrical/signal-processing.md)
- [Fourier Transform](../../signals/fourier-transform.md)
- [Sensing and Perception](../../app/robotics/sensing.md)
