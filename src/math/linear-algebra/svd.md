
# Singular Value Decomposition

## Definition

Let \\(\mathbf{A}\\) be a real \\(m \times n\\) matrix, that is, \\(\mathbf{A} \in \mathbb{R}^{m \times n}\\). The **Singular Value Decomposition (SVD)** asserts that there exist orthogonal matrices \\(\mathbf{U} \in \mathbb{R}^{m \times m}\\) and \\(\mathbf{V} \in \mathbb{R}^{n \times n}\\), and a diagonal matrix \\(\mathbf{\Sigma} \in \mathbb{R}^{m \times n}\\) with non-negative entries, such that
\\[
    \mathbf{A} = \mathbf{U} \mathbf{\Sigma} \mathbf{V}^T
\\]
where:
- \\(\mathbf{U}\\) is an orthogonal matrix (\\(\mathbf{U}^T \mathbf{U} = \mathbf{I}_m\\)),
- \\(\mathbf{V}\\) is an orthogonal matrix (\\(\mathbf{V}^T \mathbf{V} = \mathbf{I}_n\\)),
- \\(\mathbf{\Sigma}\\) is a diagonal matrix with non-negative real numbers \\(\sigma_1 \geq \sigma_2 \geq \cdots \geq \sigma_p \geq 0\\) (where \\(p = \min(m, n)\\)) on the diagonal and zeros elsewhere.

The numbers \\(\sigma_1, \ldots, \sigma_p\\) are called the **singular values** of \\(\mathbf{A}\\). The columns of \\(\mathbf{U}\\) are called the **left singular vectors**, and the columns of \\(\mathbf{V}\\) are the **right singular vectors**.

## Properties of Singular Values

- **Non-negativity:** Each singular value \\(\sigma_i\\) satisfies \\(\sigma_i \geq 0\\).
- **Uniqueness:** The singular values of \\(\mathbf{A}\\) are uniquely determined (up to ordering) by \\(\mathbf{A}\\).
- **Relation to Eigenvalues:** The nonzero singular values of \\(\mathbf{A}\\) are the square roots of the nonzero eigenvalues of both \\(\mathbf{A}^T \mathbf{A}\\) and \\(\mathbf{A} \mathbf{A}^T\\):
  \\[
      \text{If } \lambda_i \text{ is a nonzero eigenvalue of } \mathbf{A}^T \mathbf{A}, \text{ then } \sigma_i = \sqrt{\lambda_i}
  \\]
- **Ordering:** By convention, the singular values are ordered so that \\(\sigma_1 \geq \sigma_2 \geq \cdots \geq \sigma_p \geq 0\\).

## Geometric Interpretation

The SVD describes the action of \\(\mathbf{A}\\) as a composition of three linear transformations:
- \\(\mathbf{V}^T\\): a rotation or reflection in \\(\mathbb{R}^n\\),
- \\(\mathbf{\Sigma}\\): a scaling along orthogonal axes (by the singular values),
- \\(\mathbf{U}\\): a rotation or reflection in \\(\mathbb{R}^m\\).

Thus, for any vector \\(\mathbf{x} \in \mathbb{R}^n\\), the transformation \\(\mathbf{A}\mathbf{x}\\) can be interpreted as:
\\[
    \mathbf{x} \xrightarrow{\mathbf{V}^T} \text{rotate/reflect} \xrightarrow{\mathbf{\Sigma}} \text{scale} \xrightarrow{\mathbf{U}} \text{rotate/reflect}
\\]
The effect of \\(\mathbf{A}\\) is to map the unit sphere in \\(\mathbb{R}^n\\) to an ellipsoid in \\(\mathbb{R}^m\\), with the axes of the ellipsoid aligned with the left singular vectors and their lengths equal to the singular values.

## Rank, Null Space, and Condition Number

- **Rank:** The rank of \\(\mathbf{A}\\) is equal to the number of nonzero singular values:
  \\[
      \operatorname{rank}(\mathbf{A}) = \\#\{i : \sigma_i > 0\}
  \\]
- **Null Space:** The right singular vectors corresponding to zero singular values form an orthonormal basis for the null space of \\(\mathbf{A}\\).
- **Range:** The left singular vectors corresponding to nonzero singular values span the column space (range) of \\(\mathbf{A}\\).
- **Condition Number:** The (spectral) condition number of \\(\mathbf{A}\\) is the ratio of the largest to the smallest nonzero singular value:
  \\[
      \kappa(\mathbf{A}) = \frac{\sigma_1}{\sigma_r}
  \\]
  where \\(r = \operatorname{rank}(\mathbf{A})\\).

## Low-Rank Approximations and the Eckart–Young Theorem

The SVD provides a natural way to approximate a matrix by one of lower rank. For \\(k < r\\), define \\(\mathbf{A}_k\\) as:
\\[
    \mathbf{A}_k = \sum\_{i=1}^k \sigma_i \mathbf{u}_i \mathbf{v}_i^T
\\]
where \\(\mathbf{u}_i\\) and \\(\mathbf{v}_i\\) are the \\(i\\)-th columns of \\(\mathbf{U}\\) and \\(\mathbf{V}\\), respectively. The **Eckart–Young theorem** states that \\(\mathbf{A}_k\\) is the best rank-\\(k\\) approximation to \\(\mathbf{A}\\) in both the spectral norm and the Frobenius norm:
\\[
    \|\mathbf{A} - \mathbf{A}_k\|_2 = \min\_{\operatorname{rank}(\mathbf{B}) \leq k} \|\mathbf{A} - \mathbf{B}\|_2 = \sigma\_{k+1}
\\]
and
\\[
    \|\mathbf{A} - \mathbf{A}_k\|_F^2 = \sum\_{i=k+1}^r \sigma_i^2
\\]
where \\(\|\cdot\|_2\\) denotes the spectral norm and \\(\|\cdot\|_F\\) denotes the Frobenius norm.

## Applications

- **Numerical Analysis:** SVD is used for solving ill-posed linear systems, computing pseudoinverses, and numerical stability analysis.
- **Data Compression:** Low-rank approximations via SVD are used to compress images, signals, and other data by retaining only the largest singular values.
- **Principal Component Analysis (PCA):** PCA can be formulated in terms of the SVD of the data matrix, with principal components corresponding to the right singular vectors.
- **Signal Processing:** SVD is used for noise reduction, feature extraction, and blind source separation.
- **Machine Learning:** SVD underlies dimensionality reduction, latent semantic analysis in natural language processing, collaborative filtering, and more.
