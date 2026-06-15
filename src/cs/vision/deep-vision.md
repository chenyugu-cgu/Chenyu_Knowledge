# Deep Learning for Vision

Deep neural networks have transformed computer vision, learning powerful representations directly from pixels and surpassing hand-crafted methods on nearly every task. This chapter applies [deep learning](../ml/deep-learning.md) to images.

## Convolutional Neural Networks

CNNs exploit image structure with **convolutional layers** that share weights across space, capturing local patterns with translation invariance (see [Deep Learning](../ml/deep-learning.md)). Stacked conv + pooling layers build a hierarchy: edges → textures → parts → objects.

Landmark architectures: LeNet, AlexNet, VGG, **ResNet** (skip connections enable very deep nets), and EfficientNet.

## Core Vision Tasks

| Task | Output |
|---|---|
| Classification | image → label |
| Object detection | boxes + labels (YOLO, Faster R-CNN) |
| Semantic segmentation | per-pixel class (U-Net, DeepLab) |
| Instance segmentation | per-object masks (Mask R-CNN) |
| Pose estimation | keypoint locations |

**U-Net**, designed for biomedical segmentation, is a workhorse for [medical imaging](../../app/biomed/imaging.md).

## Vision Transformers

Transformers (see [Deep Learning](../ml/deep-learning.md)) treat an image as a sequence of patches and apply self-attention. **Vision Transformers (ViT)** match or beat CNNs given enough data, and underlie multimodal models.

## Training in Practice

- **Transfer learning** — start from a model pretrained on ImageNet and fine-tune; the dominant approach when data is limited (almost always in medicine).
- **Data augmentation** — flips, crops, color jitter to improve generalization.
- **Self-supervised pretraining** — learn from unlabeled images, then fine-tune.

## Considerations for Medical and Safety-Critical Use

Robustness, calibration, interpretability, and dataset bias matter enormously. A model must generalize across scanners, populations, and conditions; uncertainty estimates and validation on held-out sites are essential. See [Model Evaluation](../ml/evaluation.md).

## See Also

- [Deep Learning](../ml/deep-learning.md)
- [Medical Imaging](../../app/biomed/imaging.md)
- [Feature Detection](features.md)
