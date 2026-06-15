# Neural Networks

A neural network is a composition of simple parametric functions (neurons) that, with enough capacity, can approximate any continuous function. They are the foundation of [deep learning](deep-learning.md).

## The Neuron

A single neuron computes a weighted sum plus bias, passed through a nonlinear activation:
\\[
a = \phi\!\left(\sum_i w_i x_i + b\right) = \phi(\mathbf{w}^T\mathbf{x} + b).
\\]
Without the nonlinearity \\(\phi\\), stacking neurons would collapse to a single linear map.

## Activation Functions

| Activation | Formula | Notes |
|---|---|---|
| Sigmoid | \\(1/(1+e^{-z})\\) | saturates, vanishing gradients |
| Tanh | \\(\tanh z\\) | zero-centered |
| **ReLU** | \\(\max(0, z)\\) | default; fast, sparse |
| Leaky ReLU | \\(\max(\alpha z, z)\\) | avoids dead units |
| Softmax | \\(e^{z_i}/\sum_j e^{z_j}\\) | output layer for classification |

## Feedforward Networks

Layers transform the input in sequence:
\\[
\mathbf{a}^{(\ell)} = \phi\!\left(W^{(\ell)}\mathbf{a}^{(\ell-1)} + \mathbf{b}^{(\ell)}\right).
\\]
The **universal approximation theorem** guarantees that even one hidden layer (wide enough) can approximate any continuous function — depth makes this efficient.

## Training: Backpropagation

Training minimizes a loss \\(L\\) by gradient descent. **Backpropagation** computes \\(\partial L/\partial W\\) efficiently by the chain rule, propagating error gradients backward:
\\[
\delta^{(\ell)} = \big(W^{(\ell+1)}\big)^T\delta^{(\ell+1)} \odot \phi'(z^{(\ell)}),
\qquad
\frac{\partial L}{\partial W^{(\ell)}} = \delta^{(\ell)}\big(\mathbf{a}^{(\ell-1)}\big)^T.
\\]
Weights update via [gradient descent variants](../optimization/gradient.md) (SGD, Adam).

## Loss Functions

- **Regression:** mean squared error \\(\tfrac{1}{n}\sum(\hat{y}-y)^2\\).
- **Classification:** cross-entropy \\(-\sum_i y_i\log\hat{y}_i\\).

## A Tiny Network from Scratch (Python)

```python
import numpy as np

def sigmoid(z): return 1/(1+np.exp(-z))

rng = np.random.default_rng(0)
X = rng.normal(size=(200, 2))
y = (X[:,0]*X[:,1] > 0).astype(float).reshape(-1, 1)   # XOR-like

W1, b1 = rng.normal(size=(2,8))*0.5, np.zeros(8)
W2, b2 = rng.normal(size=(8,1))*0.5, np.zeros(1)
lr = 0.1
for epoch in range(2000):
    h = sigmoid(X@W1 + b1)
    out = sigmoid(h@W2 + b2)
    err = out - y
    dW2 = h.T @ (err*out*(1-out))
    dh = (err*out*(1-out)) @ W2.T * h*(1-h)
    dW1 = X.T @ dh
    W2 -= lr*dW2; W1 -= lr*dW1
acc = ((out > 0.5) == y).mean()
print("train accuracy:", round(float(acc), 3))
```

## See Also

- [Deep Learning](deep-learning.md)
- [Gradient Descent and Variants](../optimization/gradient.md)
- [Regularization](regularization.md)
