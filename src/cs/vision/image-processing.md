# Image Processing

Image processing transforms images to enhance them or extract low-level structure — the front end of every vision system. It is 2-D [signal processing](../../eng/electrical/signal-processing.md).

## Point Operations

Per-pixel transforms: brightness/contrast adjustment, gamma correction, thresholding (image → binary), and **histogram equalization** to spread intensities for better contrast.

## Spatial Filtering (Convolution)

Sliding a small **kernel** over the image (2-D [convolution](../../signals/convolution.md)) implements:

| Kernel | Effect |
|---|---|
| Box / Gaussian | blur, denoise |
| Laplacian | edge enhancement |
| Sobel / Prewitt | gradient (edges) |
| Sharpening | boost high frequencies |

The **Gaussian blur** is separable and the standard pre-smoothing step before edge/feature detection.

## Edge Detection

Edges are intensity discontinuities — where the gradient is large. The **Canny detector** is the classic pipeline: Gaussian smooth → gradient (Sobel) → non-maximum suppression → hysteresis thresholding. Edges feed segmentation and feature detection.

## Morphological Operations

On binary images, **erosion** and **dilation** (and their compositions, opening/closing) remove noise, fill holes, and clean up shapes — common after thresholding in medical and industrial imaging.

## Frequency-Domain Processing

The 2-D [FFT](../../signals/fourier-transform.md) enables frequency-domain filtering: low-pass (blur), high-pass (sharpen), and notch filters to remove periodic noise. The DCT underlies JPEG compression.

## Color and Channels

Color spaces (RGB, HSV, Lab) suit different tasks — HSV separates color from brightness, useful for segmentation under varying light.

## See Also

- [Feature Detection](features.md)
- [Convolution and Correlation](../../signals/convolution.md)
- [Fourier Transform](../../signals/fourier-transform.md)
