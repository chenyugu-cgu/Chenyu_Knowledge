# Machine Learning Recipes

End-to-end, reproducible recipes covering the three core ML tasks: regression, classification, and clustering. Each emphasizes correct evaluation and leakage-free pipelines.

---

## Recipe 1 — Regression with a Proper Pipeline

**Purpose.** Predict a continuous target and estimate generalization honestly.

**Background.** Wrap preprocessing and model in a single `Pipeline` so that scaling statistics come only from training folds. See [Supervised Learning](../../cs/ml/supervised.md) and [Model Evaluation](../../cs/ml/evaluation.md).

**Example (Python).**
```python
import numpy as np
from sklearn.pipeline import make_pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import Ridge
from sklearn.model_selection import cross_val_score
from sklearn.datasets import fetch_california_housing

X, y = fetch_california_housing(return_X_y=True)
pipe = make_pipeline(StandardScaler(), Ridge(alpha=1.0))
scores = cross_val_score(pipe, X, y, cv=5, scoring="r2")
print("R^2: %.3f ± %.3f" % (scores.mean(), scores.std()))
```

**Result.** A cross-validated \\(R^2\\) with its variability — a trustworthy performance estimate.

**Variations.** Swap Ridge for Lasso, gradient boosting, or random forests; tune `alpha` with `GridSearchCV`.

---

## Recipe 2 — Classification with Threshold Tuning

**Purpose.** Classify and report metrics robust to class imbalance.

**Background.** Accuracy misleads under imbalance; use ROC-AUC, precision/recall, and the confusion matrix. See [Model Evaluation](../../cs/ml/evaluation.md).

**Example (Python).**
```python
from sklearn.datasets import load_breast_cancer
from sklearn.model_selection import train_test_split
from sklearn.pipeline import make_pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report, roc_auc_score

X, y = load_breast_cancer(return_X_y=True)
Xtr, Xte, ytr, yte = train_test_split(X, y, test_size=0.3, random_state=0, stratify=y)
clf = make_pipeline(StandardScaler(), LogisticRegression(max_iter=1000)).fit(Xtr, ytr)
proba = clf.predict_proba(Xte)[:, 1]
print("ROC-AUC:", round(roc_auc_score(yte, proba), 3))
print(classification_report(yte, (proba > 0.5).astype(int)))
```

**Result.** High ROC-AUC plus a per-class precision/recall breakdown.

**Variations.** Adjust the decision threshold to trade precision vs. recall; calibrate probabilities; handle imbalance with class weights or resampling.

---

## Recipe 3 — Cluster and Choose k

**Purpose.** Discover groups in unlabeled data and pick the number of clusters.

**Background.** K-means minimizes within-cluster variance; the silhouette score evaluates cluster quality without labels. See [Unsupervised Learning](../../cs/ml/unsupervised.md).

**Example (Python).**
```python
import numpy as np
from sklearn.cluster import KMeans
from sklearn.metrics import silhouette_score

rng = np.random.default_rng(0)
X = np.vstack([rng.normal(c, 0.6, (150, 2)) for c in ([0,0],[4,4],[0,5],[5,0])])

for k in range(2, 7):
    labels = KMeans(n_clusters=k, n_init=10, random_state=0).fit_predict(X)
    print(f"k={k}: silhouette={silhouette_score(X, labels):.3f}")
```

**Result.** The silhouette score peaks at the true number of clusters (here \\(k=4\\)).

**Variations.** Use the elbow method on inertia; try DBSCAN for non-spherical clusters or unknown \\(k\\).

## References

- [Supervised Learning](../../cs/ml/supervised.md)
- [Regularization](../../cs/ml/regularization.md)
- [Feature Engineering](../../cs/ml/features.md)
