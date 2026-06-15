# Feature Engineering

Feature engineering transforms raw data into representations that expose the signal to a model. Despite the rise of representation learning, well-crafted features often beat fancier algorithms on tabular data — "garbage in, garbage out" still rules.

## Numerical Features

- **Scaling:** standardize (\\(z = (x-\mu)/\sigma\\)) or min–max normalize so features share a comparable range — essential for distance- and gradient-based methods.
- **Nonlinear transforms:** log, square root, or Box–Cox to tame skew and stabilize variance.
- **Binning / discretization:** convert continuous values into ordinal buckets to capture nonlinearity.
- **Polynomial & interaction terms:** \\(x_1 x_2,\ x^2\\) let linear models fit curved relationships.

## Categorical Features

| Encoding | When |
|---|---|
| One-hot | low-cardinality, no order |
| Ordinal | natural ordering |
| Target/mean encoding | high-cardinality (guard against leakage) |
| Embeddings | very high cardinality, neural models |

## Temporal and Cyclical Features

Extract day-of-week, month, lags, and rolling statistics for time series. Encode cyclic variables (hour, angle) with sine/cosine so that 23:00 and 00:00 are close:
\\[
x_{\sin} = \sin\frac{2\pi t}{T}, \qquad x_{\cos} = \cos\frac{2\pi t}{T}.
\\]

## Text and Images

- **Text:** bag-of-words, TF-IDF, n-grams, or learned embeddings.
- **Images:** historically hand-crafted (SIFT, HOG); now learned by [CNNs](deep-learning.md).

## Feature Selection

Reduce dimensionality and noise:
- **Filter:** correlation, mutual information, variance threshold.
- **Wrapper:** recursive feature elimination.
- **Embedded:** L1/Lasso penalties (see [Regularization](regularization.md)), tree feature importances.

## Handling Missing Data

Impute (mean/median, k-NN, model-based) or add a "missing" indicator. The pattern of missingness can itself be informative.

## The Golden Rule: No Leakage

Fit all transformations (scalers, encoders, imputers) on the **training fold only**, then apply to validation/test. Use a pipeline so the same steps run consistently:

```python
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression

pipe = Pipeline([
    ("scale", StandardScaler()),
    ("clf", LogisticRegression(max_iter=1000)),
])
# pipe.fit(X_train, y_train) scales using only training statistics
```

## See Also

- [Data Cleaning](../data/cleaning.md)
- [Regularization](regularization.md)
- [Model Evaluation](evaluation.md)
