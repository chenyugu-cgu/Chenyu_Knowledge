# Regularization

Regularization combats overfitting by constraining model complexity — trading a little training accuracy for much better generalization. It is the practical embodiment of Occam's razor.

## The Idea

Add a penalty \\(\Omega(\theta)\\) to the loss:
\\[
\min_\theta\ \frac{1}{n}\sum_i \ell(f_\theta(x_i), y_i) + \lambda\,\Omega(\theta),
\\]
where \\(\lambda \ge 0\\) controls the strength. Larger \\(\lambda\\) → simpler model → higher bias, lower variance.

## L2 (Ridge) and L1 (Lasso)

- **L2 / Ridge:** \\(\Omega = \lVert\theta\rVert_2^2\\). Shrinks weights smoothly toward zero; stabilizes ill-conditioned problems. The solution is \\(\hat{\theta} = (X^TX + \lambda I)^{-1}X^Ty\\).
- **L1 / Lasso:** \\(\Omega = \lVert\theta\rVert_1\\). Drives many weights to **exactly zero**, performing feature selection. Non-differentiable at zero; solved by coordinate descent or proximal methods.
- **Elastic Net:** a blend \\(\alpha\lVert\theta\rVert_1 + (1-\alpha)\lVert\theta\rVert_2^2\\) — sparsity plus stability under correlated features.

Both are convex programs — see [Convex Optimization](../optimization/convex.md).

## Bayesian View

L2 is equivalent to a Gaussian prior on the weights; L1 to a Laplace prior. Regularization is **MAP estimation** with that prior — connecting to [Bayesian Inference](../../math/probability/bayes.md).

## Regularization in Neural Networks

| Technique | Mechanism |
|---|---|
| **Weight decay** | L2 penalty on weights |
| **Dropout** | randomly zero activations during training |
| **Early stopping** | halt when validation loss rises |
| **Data augmentation** | synthetic input variation |
| **Batch normalization** | implicit regularization + stability |
| **Label smoothing** | soften one-hot targets |

## Choosing \\(\lambda\\)

Select by cross-validation: sweep \\(\lambda\\) on a log scale and pick the value minimizing validation error (often the largest \\(\lambda\\) within one standard error of the best — the "1-SE rule" — for a simpler model).

## Example: Lasso Path

```python
import numpy as np
from sklearn.linear_model import LassoCV

rng = np.random.default_rng(0)
X = rng.normal(size=(200, 50))
true = np.zeros(50); true[:5] = [3, -2, 1.5, 0, 4]   # only 4 truly nonzero
y = X @ true + rng.normal(0, 0.5, 200)

model = LassoCV(cv=5).fit(X, y)
print("chosen alpha:", round(model.alpha_, 4))
print("nonzero coefficients:", int(np.sum(model.coef_ != 0)))   # ~4–6
```

## See Also

- [Model Evaluation](evaluation.md) — bias–variance tradeoff.
- [Convex Optimization](../optimization/convex.md)
- [Bayesian Inference](../../math/probability/bayes.md)
