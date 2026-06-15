# Solving Linear Systems

Solving \\(A\mathbf{x} = \mathbf{b}\\) is the single most common task in scientific computing — circuit analysis, structural FEA, regression, and the inner loop of countless algorithms all reduce to it.

## Direct Methods

- **Gaussian elimination / LU decomposition** — factor \\(A = LU\\), then solve by forward/back substitution. \\(O(n^3)\\) to factor, \\(O(n^2)\\) per right-hand side. **Partial pivoting** is essential for [numerical stability](floating-point.md).
- **Cholesky** — for symmetric positive-definite \\(A\\), twice as fast as LU; ubiquitous in least squares and optimization.
- **QR decomposition** — stable for least-squares and rank-deficient problems.

## Iterative Methods

For large, sparse systems (FEA, PDEs), direct factorization is too costly. Iterative methods refine a guess using only matrix–vector products:
- **Conjugate gradient (CG)** — for symmetric positive-definite systems; converges in \\(\le n\\) steps, far fewer when well-conditioned.
- **GMRES, BiCGSTAB** — for general nonsymmetric systems.

**Preconditioning** transforms the system to improve conditioning and dramatically speed convergence.

## Conditioning

The **condition number** \\(\kappa(A)\\) bounds how input error propagates to the solution:
\\[
\frac{\|\Delta x\|}{\|x\|} \le \kappa(A)\frac{\|\Delta b\|}{\|b\|}.
\\]
Large \\(\kappa\\) (ill-conditioned) means small data errors blow up — common with nearly dependent rows/columns.

## Least Squares (Overdetermined Systems)

When \\(A\\) is tall (more equations than unknowns), solve the **normal equations** \\(A^TA\mathbf{x} = A^T\mathbf{b}\\), or more stably via QR or the [SVD](../../math/linear-algebra/svd.md). This is the engine of [linear regression](../data/modeling.md) and curve fitting.

## Practical Advice

Use battle-tested libraries (LAPACK/BLAS via NumPy/SciPy) rather than rolling your own; exploit structure (sparse, symmetric, banded); and monitor the condition number before trusting a solution.

## See Also

- [Matrix Operations](../../math/linear-algebra/matrices.md)
- [Singular Value Decomposition](../../math/linear-algebra/svd.md)
- [Floating-Point and Error](floating-point.md)
