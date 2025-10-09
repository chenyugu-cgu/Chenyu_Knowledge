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

```rust
use linfa::prelude::*;
use linfa_linear::RidgeRegression;
use ndarray::Array2;
use ndarray_rand::RandomExt;
use ndarray_rand::rand_distr::Normal;
use rand::SeedableRng;
use rand_isaac::Isaac64Rng;

fn main() {
    let mut rng = Isaac64Rng::seed_from_u64(0);
    let n = 500;
    let d = 20;
    let X: Array2<f64> = Array2::random_using((n, d), Normal::new(0.,1.).unwrap(), &mut rng);
    let mut w_true = vec![3., -2., 0., 1.];
    w_true.extend(vec![0.; d-4]);
    let w_true = ndarray::Array1::from(w_true);
    let noise: Array2<f64> = Array2::random_using((n,1), Normal::new(0.,1.).unwrap(), &mut rng);
    let y = X.dot(&w_true) + noise.column(0);

    // Train/test split
    let test_size = 0.2;
    let train_size = (n as f64 * (1.0 - test_size)) as usize;
    let (X_tr, X_te) = X.view().split_at(Axis(0), train_size);
    let (y_tr, y_te) = y.view().split_at(Axis(0), train_size);

    let alphas = linspace(1e-3, 1e2, 20);
    let mut best_rmse = f64::INFINITY;
    let mut best_alpha = 0.0;
    for &alpha in alphas.iter() {
        let model = RidgeRegression::params().alpha(alpha).fit(&X_tr.to_owned(), &y_tr.to_owned()).unwrap();
        let y_pred = model.predict(&X_te.to_owned());
        let rmse = ((&y_te - &y_pred).mapv(|x| x.powi(2)).mean().unwrap()).sqrt();
        if rmse < best_rmse {
            best_rmse = rmse;
            best_alpha = alpha;
        }
    }
    println!("alpha*: {}", best_alpha);
    println!("RMSE: {}", best_rmse);
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
