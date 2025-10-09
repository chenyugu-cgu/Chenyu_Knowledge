# Machine Learning

Machine Learning (ML) provides statistical and computational methods for learning patterns from data in order to **predict**, **classify**, or **control** systems. This section presents a **scientific, cookbook-style** reference: concise background → inputs (ingredients) → step-by-step methods → worked examples → validated results.

## Scope and Structure

- **Supervised learning** (this chapter’s focus): regression and classification with labeled data.
- **Unsupervised learning**: clustering, dimensionality reduction.
- **Model evaluation**: cross-validation, metrics, uncertainty.
- **Regularization & optimization**: bias–variance trade-off, convex/nonconvex methods.
- **Engineering practice**: data pipelines, feature scaling, reproducibility.

## Prerequisites

- Linear algebra (vectors, matrices, eigen/SVD)
- Calculus (gradient, chain rule)
- Probability & statistics (distributions, expectations)
- Numerical optimization (gradient descent, line search)

## Notation and Conventions

- Dataset \(\mathcal{D}=\{(x_i, y_i)\}_{i=1}^n\) with \(x_i \in \mathbb{R}^d\).
- Regression target \(y \in \mathbb{R}\); classification target \(y \in \{0,1\}\) (binary) or \(\{1,\dots,K\}\).
- Loss \(\mathcal{L}(\theta)\) minimized w.r.t. model parameters \(\theta\) (e.g., MSE, logistic loss).
- Train/Validation/Test: **60/20/20** split by default, or **k-fold** cross-validation.

## Recipe Format (used throughout the ML section)

1. **Purpose** — What is the task (e.g., “predict force from displacement”).
2. **Background** — Model equation + assumptions.
3. **Ingredients** — Data, hyperparameters, libraries.
4. **Method** — Step-by-step procedure.
5. **Example** — Minimal code in Python, MATLAB, and Rust.
6. **Result** — Metrics + interpretation.
7. **Variations** — Alternatives (e.g., Lasso vs Ridge, SVM vs Logistic).
8. **References** — Textbooks/papers.

---

## Quick Start: Linear Regression (Regression)

**Purpose.** Fit \(y \approx \beta_0 + \beta^\top x\) by minimizing MSE.

**Background.** Closed-form (normal equations) or iterative (gradient descent). Regularization (Ridge/Lasso) mitigates overfitting and multicollinearity.

### Python (NumPy + scikit-learn)

```python
# Quick linear regression demo
import numpy as np
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score
from sklearn.model_selection import train_test_split

rng = np.random.default_rng(42)
n, d = 400, 1
X = rng.uniform(-2, 2, size=(n, d))
y = 3.0 * X[:, 0] - 1.2 + rng.normal(0, 0.5, size=n)

X_tr, X_te, y_tr, y_te = train_test_split(X, y, test_size=0.2, random_state=42)
model = LinearRegression().fit(X_tr, y_tr)
y_hat = model.predict(X_te)

print("coef_:", model.coef_, "intercept_:", model.intercept_)
print("MSE:", mean_squared_error(y_te, y_hat))
print("R^2:", r2_score(y_te, y_hat))
```

### MATLAB

```matlab
% Quick linear regression demo
rng(42);
n = 400; d = 1;
X = -2 + 4*rand(n,d);
y = 3.0 * X(:,1) - 1.2 + 0.5*randn(n,1);

cv = cvpartition(n,'HoldOut',0.2);
X_tr = X(training(cv),:);
y_tr = y(training(cv));
X_te = X(test(cv),:);
y_te = y(test(cv));

beta = regress(y_tr, [ones(size(X_tr,1),1), X_tr]);

y_hat = [ones(size(X_te,1),1), X_te] * beta;

fprintf('coef_: %f\n', beta(2));
fprintf('intercept_: %f\n', beta(1));
mse = mean((y_te - y_hat).^2);
fprintf('MSE: %f\n', mse);
r2 = 1 - sum((y_te - y_hat).^2)/sum((y_te - mean(y_te)).^2);
fprintf('R^2: %f\n', r2);
```

### Rust

