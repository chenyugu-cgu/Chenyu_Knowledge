# Model Evaluation

A model is only as trustworthy as its evaluation. Good evaluation estimates how a model will perform on **unseen** data and guards against the cardinal sin of overfitting to the test set.

## Train / Validation / Test Splits

- **Training set** — fit parameters.
- **Validation set** — tune hyperparameters and select models.
- **Test set** — a final, untouched estimate of generalization.

Never let test data influence any decision. For small datasets, **k-fold cross-validation** averages performance over \\(k\\) splits for a lower-variance estimate.

## The Bias–Variance Tradeoff

Expected error decomposes as
\\[
\mathbb{E}[(\hat{f}(x) - y)^2] = \underbrace{(\text{Bias})^2}_{\text{underfit}} + \underbrace{\text{Variance}}_{\text{overfit}} + \underbrace{\sigma^2}_{\text{irreducible}}.
\\]
Simple models underfit (high bias); complex models overfit (high variance). The art is balancing the two — see [Regularization](regularization.md).

## Regression Metrics

\\[
\text{RMSE} = \sqrt{\tfrac{1}{n}\sum(\hat{y}-y)^2}, \quad
\text{MAE} = \tfrac{1}{n}\sum|\hat{y}-y|, \quad
R^2 = 1 - \frac{\sum(\hat{y}-y)^2}{\sum(\bar{y}-y)^2}.
\\]

## Classification Metrics

From the confusion matrix (TP, FP, TN, FN):
\\[
\text{Precision} = \frac{TP}{TP+FP}, \quad
\text{Recall} = \frac{TP}{TP+FN}, \quad
F_1 = \frac{2\,PR}{P+R}.
\\]
- **ROC-AUC** — ranking quality across all thresholds; robust to class balance changes.
- **PR-AUC** — preferred for heavily imbalanced classes.
- **Log loss** — penalizes confident wrong predictions; rewards calibration.

Accuracy alone is misleading under class imbalance (a 99%-negative dataset is 99% accurate by predicting "negative" always).

## Calibration

A model is **calibrated** if predicted probabilities match observed frequencies. Check with reliability diagrams and the **Brier score**; fix with Platt scaling or isotonic regression.

## Pitfalls

- **Data leakage** — information from the future or the target sneaks into features (e.g., scaling before splitting).
- **Distribution shift** — train and deploy distributions differ.
- **Multiple-comparison bias** — testing many models inflates apparent performance; hold out a final test set.

## Example: Cross-Validated Scoring

```python
from sklearn.model_selection import cross_val_score
from sklearn.ensemble import RandomForestClassifier
from sklearn.datasets import load_breast_cancer

X, y = load_breast_cancer(return_X_y=True)
clf = RandomForestClassifier(n_estimators=200, random_state=0)
scores = cross_val_score(clf, X, y, cv=5, scoring="roc_auc")
print("ROC-AUC: %.3f ± %.3f" % (scores.mean(), scores.std()))
```

## See Also

- [Regularization](regularization.md)
- [Statistical Estimation](../../math/probability/estimation.md)
- [Hypothesis Testing](../../math/probability/hypothesis-testing.md)
