# Deep Learning

Deep learning uses neural networks with many layers and specialized architectures to learn hierarchical representations directly from raw data. It powers modern vision, speech, language, and generative AI.

## Why Depth Helps

Each layer composes features from the previous one — edges → textures → parts → objects. Depth lets a network represent complex functions with exponentially fewer parameters than a shallow one, and learn features automatically instead of hand-engineering them.

## Convolutional Neural Networks (CNNs)

For images and grids, **convolutional layers** share weights across space, exploiting locality and translation invariance:
\\[
(I * K)(i,j) = \sum_{m,n} I(i+m, j+n)\,K(m,n).
\\]
Stacked with pooling and nonlinearities, CNNs dominate image classification, detection, and segmentation. Architectures: LeNet, AlexNet, VGG, ResNet (skip connections enable very deep nets).

## Recurrent Networks and Sequences

**RNNs**, **LSTMs**, and **GRUs** process sequences with hidden state carrying information across time — used for time series, speech, and (historically) language. Gating mitigates vanishing gradients over long sequences.

## Transformers and Attention

The **attention** mechanism lets every position attend to every other:
\\[
\text{Attention}(Q,K,V) = \text{softmax}\!\left(\frac{QK^T}{\sqrt{d_k}}\right)V.
\\]
**Transformers** stack self-attention and feedforward blocks, parallelize across sequence length, and are the backbone of large language models and modern vision.

## Training at Scale

- **Optimizers:** Adam/AdamW with learning-rate warmup and decay.
- **Regularization:** dropout, weight decay, data augmentation, early stopping — see [Regularization](regularization.md).
- **Normalization:** batch/layer normalization stabilizes and speeds training.
- **Transfer learning:** fine-tune a pretrained model on your task — the dominant practical paradigm.

## Generative Models

- **Autoencoders / VAEs** learn compressed latent representations.
- **GANs** pit a generator against a discriminator.
- **Diffusion models** learn to denoise, producing state-of-the-art images.
- **Autoregressive transformers** generate text and code token by token.

## Practical Workflow (PyTorch sketch)

```python
import torch, torch.nn as nn

model = nn.Sequential(
    nn.Linear(784, 256), nn.ReLU(),
    nn.Dropout(0.2),
    nn.Linear(256, 10),
)
loss_fn = nn.CrossEntropyLoss()
opt = torch.optim.AdamW(model.parameters(), lr=1e-3)

# one training step (x: [B,784], y: [B])
def step(x, y):
    opt.zero_grad()
    loss = loss_fn(model(x), y)
    loss.backward()
    opt.step()
    return loss.item()
```

## See Also

- [Neural Networks](neural-networks.md)
- [Gradient Descent and Variants](../optimization/gradient.md)
- [Machine Learning Recipes](../../cookbook/examples/ml.md)
