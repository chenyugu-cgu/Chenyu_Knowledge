# Supervised Learning

Supervised learning estimates a mapping \\(f: \mathbb{R}^d \to \mathbb{R}\\) (regression) or \\(f: \mathbb{R}^d \to \{1,\dots,K\}\\) (classification) using labeled examples. This chapter provides a formal overview and cookbook recipes with minimal, reproducible code.

## 1. Problem Setup

Given \\(\mathcal{D} = \{(x_i, y_i)\}_{i=1}^n\\), learn parameters \\(\theta\\) of \\(f_\theta\\) by minimizing empirical risk:
\\[
\min_\theta \ \frac{1}{n}\sum_{i=1}^n \ell\big(f_\theta(x_i), y_i\big) + \lambda \Omega(\theta),
\\]
where \\(\ell\\) is a task-specific loss (MSE, logistic, cross-entropy) and \\(\Omega\\) encodes regularization (e.g., \\(\|\theta\|_2^2\\)).

## 2. Workflow (Cookbook)

1. **Define the task** (regression/classification).
2. **Prepare data** (clean, split: train/val/test or k-fold).
3. **Baseline model** (linear/logistic).
4. **Regularization** (Ridge/Lasso; weight decay).
5. **Hyperparameter search** (grid/random/Bayesian).
6. **Diagnostics** (learning curves, residuals, calibration).
7. **Report** (metrics + uncertainty; assumptions; limitations).

## 3. Metrics

- Regression: RMSE, MAE, \\(R^2\\).
- Classification: Accuracy, Precision/Recall/F1, ROC-AUC, PR-AUC, log-loss.
- Calibration: reliability diagrams; Brier score.

## 4. Example A — Ridge Regression (Python / MATLAB / Notes)

### Python

```python
import numpy as np
from sklearn.linear_model import RidgeCV
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score

rng = np.random.default_rng(0)
n, d = 500, 20
X = rng.normal(size=(n, d))
w_true = np.array([3, -2, 0, 1] + [0]*(d-4))
y = X @ w_true + rng.normal(0, 1.0, size=n)

X_tr, X_te, y_tr, y_te = train_test_split(X, y, test_size=0.2, random_state=0)
alphas = np.logspace(-3, 2, 20)
model = RidgeCV(alphas=alphas, store_cv_values=True).fit(X_tr, y_tr)
y_hat = model.predict(X_te)
print("alpha*:", model.alpha_)
print("RMSE:", mean_squared_error(y_te, y_hat, squared=False))
print("R^2:", r2_score(y_te, y_hat))
```

### MATLAB

```matlab
rng(0);
n = 500; d = 20;
X = randn(n,d);
w_true = [3; -2; 0; 1; zeros(d-4,1)];
y = X*w_true + randn(n,1);

cv = cvpartition(n,'HoldOut',0.2);
X_tr = X(training(cv),:); y_tr = y(training(cv));
X_te = X(test(cv),:); y_te = y(test(cv));

alphas = logspace(-3,2,20);
rmse = zeros(length(alphas),1);
for i = 1:length(alphas)
    w = (X_tr'*X_tr + alphas(i)*eye(d)) \ (X_tr'*y_tr);
    y_pred = X_te*w;
    rmse(i) = sqrt(mean((y_te - y_pred).^2));
end
[~, idx] = min(rmse);
alpha_star = alphas(idx);
fprintf('alpha*: %g\n', alpha_star);
fprintf('RMSE: %g\n', rmse(idx));
```

### Rust

A dependency-free ridge regression by batch gradient descent (runnable in the
playground — click ▶):

```rust
// Ridge regression: minimize ||Xw - y||^2 + lambda * ||w||^2 by gradient descent.
fn main() {
    // y = 3*x0 - 2*x1 (no noise)
    let xs = [[1.0, 2.0], [2.0, 1.0], [3.0, 0.0], [0.0, 4.0], [4.0, 2.0]];
    let ys = [-1.0, 4.0, 9.0, -8.0, 8.0];
    let (n, d) = (xs.len(), 2);
    let (lambda, lr) = (0.1_f64, 0.01_f64);
    let mut w = vec![0.0_f64; d];

    for _ in 0..5000 {
        let mut grad = vec![0.0_f64; d];
        for i in 0..n {
            let pred: f64 = (0..d).map(|j| w[j] * xs[i][j]).sum();
            let err = pred - ys[i];
            for j in 0..d {
                grad[j] += err * xs[i][j];
            }
        }
        for j in 0..d {
            grad[j] = grad[j] / n as f64 + lambda * w[j];
            w[j] -= lr * grad[j];
        }
    }
    println!("learned weights: {:?}", w); // ~ [3.0, -2.0]
}
```

## 5. Example B — Logistic Classification (Python / MATLAB / Rust)

### Python

```python
import numpy as np
from sklearn.linear_model import LogisticRegressionCV
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, log_loss

rng = np.random.default_rng(1)
n, d = 1000, 10
X = rng.normal(size=(n, d))
w_true = np.array([1, -1, 0.5] + [0]*(d-3))
logits = X @ w_true
prob = 1 / (1 + np.exp(-logits))
y = rng.binomial(1, prob)

X_tr, X_te, y_tr, y_te = train_test_split(X, y, test_size=0.3, random_state=1)
model = LogisticRegressionCV(cv=5, penalty='l2', solver='lbfgs', max_iter=1000).fit(X_tr, y_tr)
y_prob = model.predict_proba(X_te)[:,1]
y_pred = model.predict(X_te)
print("Accuracy:", accuracy_score(y_te, y_pred))
print("Log loss:", log_loss(y_te, y_prob))
```

### MATLAB

```matlab
rng(1);
n = 1000; d = 10;
X = randn(n,d);
w_true = [1; -1; 0.5; zeros(d-3,1)];
logits = X*w_true;
prob = 1./(1+exp(-logits));
y = rand(n,1) < prob;

cv = cvpartition(n,'HoldOut',0.3);
X_tr = X(training(cv),:); y_tr = y(training(cv));
X_te = X(test(cv),:); y_te = y(test(cv));

B = mnrfit(X_tr, categorical(y_tr));
pihat = mnrval(B, X_te);
[~, y_pred] = max(pihat, [], 2);
accuracy = mean(y_pred-1 == y_te);
logloss = -mean(y_te.*log(pihat(:,2)) + (1 - y_te).*log(pihat(:,1)));
fprintf('Accuracy: %.4f\n', accuracy);
fprintf('Log loss: %.4f\n', logloss);
```

### Rust

A dependency-free logistic regression by gradient descent:

```rust
fn sigmoid(z: f64) -> f64 {
    1.0 / (1.0 + (-z).exp())
}

fn main() {
    // 1-D feature; classes split near x = 0
    let xs = [-2.0, -1.0, -0.5, 0.5, 1.0, 2.0];
    let ys = [0.0, 0.0, 0.0, 1.0, 1.0, 1.0];
    let n = xs.len();
    let (mut w, mut b) = (0.0_f64, 0.0_f64);
    let lr = 0.5_f64;

    for _ in 0..2000 {
        let (mut gw, mut gb) = (0.0_f64, 0.0_f64);
        for i in 0..n {
            let err = sigmoid(w * xs[i] + b) - ys[i];
            gw += err * xs[i];
            gb += err;
        }
        w -= lr * gw / n as f64;
        b -= lr * gb / n as f64;
    }

    let correct = (0..n)
        .filter(|&i| (sigmoid(w * xs[i] + b) > 0.5) == (ys[i] > 0.5))
        .count();
    println!("w={:.3} b={:.3} accuracy={}/{}", w, b, correct, n);
}
```

