# Gradient Descent and Variants

Gradient descent is the workhorse of large-scale optimization and the algorithm that trains nearly every neural network. It takes steps downhill along the negative gradient.

## The Basic Update

\\[
\mathbf{x}_{k+1} = \mathbf{x}_k - \alpha\,\nabla f(\mathbf{x}_k),
\\]
where \\(\alpha\\) is the **learning rate**. Too large diverges; too small crawls. For convex \\(L\\)-smooth functions, \\(\alpha = 1/L\\) guarantees convergence at rate \\(O(1/k)\\).

## Stochastic Gradient Descent (SGD)

When the objective is a sum over data, \\(f = \frac{1}{n}\sum_i f_i\\), computing the full gradient is expensive. **SGD** uses a random sample (mini-batch):
\\[
\mathbf{x}_{k+1} = \mathbf{x}_k - \alpha\,\nabla f_{i_k}(\mathbf{x}_k).
\\]
Cheap, noisy steps scale to massive datasets; the noise even helps escape shallow minima. A decaying learning rate ensures convergence.

## Momentum

Accelerate by accumulating past gradients, damping oscillation across ravines:
\\[
\mathbf{v}_{k+1} = \beta\mathbf{v}_k + \nabla f(\mathbf{x}_k), \qquad
\mathbf{x}_{k+1} = \mathbf{x}_k - \alpha\mathbf{v}_{k+1}.
\\]
**Nesterov** momentum looks ahead before computing the gradient, improving the rate to \\(O(1/k^2)\\) for convex problems.

## Adaptive Methods

Per-parameter learning rates adapt to gradient history:

| Method | Idea |
|---|---|
| AdaGrad | divide by accumulated squared gradients (decays \\(\alpha\\)) |
| RMSProp | exponential moving average of squared gradients |
| **Adam** | momentum + RMSProp; the default for deep learning |

Adam's update combines first and second moment estimates with bias correction.

## Practical Guidance

- **Normalize/scale features** so curvature is balanced.
- **Tune the learning rate** first — it matters most; use warmup and schedules (cosine, step decay).
- **Batch size** trades gradient noise against hardware efficiency.
- **Watch for divergence** (loss explodes → lower \\(\alpha\\)) and plateaus (→ schedule or different optimizer).

## Minimal Implementation

```python
import numpy as np

def gradient_descent(grad, x0, lr=0.1, steps=1000, tol=1e-8):
    x = np.array(x0, dtype=float)
    for _ in range(steps):
        g = grad(x)
        x_new = x - lr * g
        if np.linalg.norm(x_new - x) < tol:
            break
        x = x_new
    return x

# Minimize f(x) = (x-3)^2  ->  grad = 2(x-3)
print(gradient_descent(lambda x: 2*(x-3), x0=[0.0]))   # ~[3.0]
```

## See Also

- [Unconstrained Optimization](unconstrained.md)
- [Deep Learning](../ml/deep-learning.md)
- [Optimization Recipes](../../cookbook/examples/optimization.md)
