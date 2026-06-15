# Unsupervised Learning

Unsupervised learning finds structure in **unlabeled** data — clusters, low-dimensional representations, density. It answers "what patterns are here?" rather than "predict this label."

## Clustering

Group similar points without labels.

### K-Means

Partition \\(n\\) points into \\(k\\) clusters by minimizing within-cluster variance:
\\[
\min_{\{C_j\}} \sum_{j=1}^{k}\sum_{x\in C_j}\lVert x - \mu_j\rVert^2.
\\]
**Lloyd's algorithm** alternates: assign each point to its nearest centroid, then recompute centroids. Fast and simple, but assumes spherical clusters and needs \\(k\\) chosen in advance (use the elbow or silhouette method). `k-means++` initialization improves results.

### Hierarchical and Density-Based

- **Hierarchical** clustering builds a dendrogram by repeatedly merging (agglomerative) or splitting clusters — no need to fix \\(k\\) upfront.
- **DBSCAN** groups dense regions and labels sparse points as noise; it finds arbitrary shapes and the number of clusters automatically.
- **Gaussian Mixture Models (GMM)** fit soft, elliptical clusters via Expectation–Maximization.

## Dimensionality Reduction

Compress high-dimensional data while preserving structure.

### Principal Component Analysis (PCA)

Project onto the directions of maximum variance — the top eigenvectors of the covariance matrix (equivalently the top singular vectors). See [Singular Value Decomposition](../../math/linear-algebra/svd.md). PCA decorrelates features, denoises, compresses, and aids visualization. The explained-variance ratio guides how many components to keep.

### Nonlinear Methods

- **t-SNE** and **UMAP** produce 2-D/3-D embeddings that preserve local neighborhoods — excellent for visualization (but not for downstream metric use).
- **Autoencoders** learn nonlinear compressions with neural networks.

## Anomaly Detection

Model normal behavior and flag outliers — isolation forests, one-class SVM, or density thresholds. Used in fraud detection, fault monitoring, and quality control.

## Example: K-Means in Python

```python
import numpy as np
from sklearn.cluster import KMeans

rng = np.random.default_rng(0)
X = np.vstack([rng.normal(m, 0.5, (100, 2)) for m in ([0,0], [5,5], [0,5])])
km = KMeans(n_clusters=3, n_init=10, random_state=0).fit(X)
print("centroids:\n", km.cluster_centers_.round(1))
print("inertia:", round(km.inertia_, 1))
```

## See Also

- [Singular Value Decomposition](../../math/linear-algebra/svd.md)
- [Feature Engineering](features.md)
- [Supervised Learning](supervised.md)
