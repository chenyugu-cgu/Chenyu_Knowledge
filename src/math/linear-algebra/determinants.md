
# Determinants

The determinant is a scalar quantity associated with a square matrix that encapsulates important algebraic and geometric properties of the corresponding linear transformation. Determinants play a central role in linear algebra, providing criteria for invertibility, volume scaling, and connections to eigenvalues and characteristic polynomials.

## Definition of the Determinant

Let \\(A = [a_{ij}]\\) be an \\(n \times n\\) square matrix over a field (such as \\(\mathbb{R}\\) or \\(\mathbb{C}\\)). The determinant of \\(A\\), denoted \\(\det(A)\\) or \\(|A|\\), is defined recursively as follows:

- For \\(n = 1\\), \\(\det([a_{11}]) = a_{11}\\).
- For \\(n \geq 2\\),
  \\[
  \det(A) = \sum_{j=1}^{n} (-1)^{1+j} a_{1j} \det(A_{1j})
  \\]
  where \\(A_{1j}\\) is the \\((n-1) \times (n-1)\\) submatrix obtained by deleting the first row and the \\(j\\)-th column of \\(A\\). This is the cofactor expansion along the first row. The definition is independent of the choice of row or column.

Alternatively, the determinant can be defined as a sum over permutations:
  \\[
  \det(A) = \sum_{\sigma \in S_n} \operatorname{sgn}(\sigma) \prod_{i=1}^n a_{i, \sigma(i)}
  \\]
where \\(S_n\\) is the symmetric group of all permutations of \\(\{1,2,\ldots,n\}\\), and \\(\operatorname{sgn}(\sigma)\\) is the sign of the permutation \\(\sigma\\).

## Properties of Determinants

Determinants satisfy several fundamental properties:

- **Multilinearity:** The determinant is linear in each row and each column separately. For example, if a row is replaced by a linear combination of two rows, the determinant is the corresponding linear combination of the determinants.

- **Alternating Property:** If two rows (or columns) of a matrix are equal, then \\(\det(A) = 0\\). More generally, interchanging two rows (or columns) multiplies the determinant by \\(-1\\).

- **Effect of Row and Column Operations:**
  - Adding a multiple of one row to another does not change the determinant.
  - Multiplying a row (or column) by a scalar \\(\lambda\\) multiplies the determinant by \\(\lambda\\).
  - Swapping two rows (or columns) multiplies the determinant by \\(-1\\).

- **Determinant of Product:** For any two \\(n \times n\\) matrices \\(A\\) and \\(B\\),
  \\[
  \det(AB) = \det(A)\det(B)
  \\]

- **Determinant of the Transpose:** For any \\(n \times n\\) matrix \\(A\\),
  \\[
  \det(A^T) = \det(A)
  \\]

## Computation Methods

### Cofactor Expansion

The determinant can be computed by expanding along any row or column using cofactors:
  \\[
  \det(A) = \sum_{j=1}^{n} a_{ij} C_{ij}
  \\]
where \\(C_{ij} = (-1)^{i+j} \det(A_{ij})\\) is the cofactor of entry \\(a_{ij}\\).

### Row Reduction

The determinant can also be computed using row reduction (Gaussian elimination) to bring the matrix to upper triangular form. The determinant is then the product of the diagonal entries, adjusted for any row swaps (which introduce a factor of \\(-1\\)) and row scalings.

## Determinant and Invertibility

A square matrix \\(A\\) is **invertible** (nonsingular) if and only if \\(\det(A) \neq 0\\). If \\(\det(A) = 0\\), the matrix is singular and does not have an inverse. The determinant thus provides a criterion for invertibility.

## Determinant as Volume Scaling Factor

Geometrically, the absolute value \\(|\det(A)|\\) represents the scaling factor by which the linear transformation defined by \\(A\\) changes volumes in \\(\mathbb{R}^n\\). For example, if \\(S\\) is a region in \\(\mathbb{R}^n\\), then the volume of \\(A(S)\\) is \\(|\det(A)|\\) times the volume of \\(S\\). The sign of \\(\det(A)\\) indicates whether the orientation is preserved or reversed.

## Special Cases

- **Triangular and Diagonal Matrices:** If \\(A\\) is upper or lower triangular, or diagonal, then
  \\[
  \det(A) = \prod_{i=1}^n a_{ii}
  \\]
  (the product of the diagonal entries).

- **Orthogonal Matrices:** If \\(Q\\) is an orthogonal matrix (\\(Q^T Q = I\\)), then \\(\det(Q) = \pm 1\\).

- **Unitary Matrices:** If \\(U\\) is a unitary matrix (\\(U^* U = I\\)), then \\(|\det(U)| = 1\\).

## Theoretical Importance

- **Eigenvalues and Characteristic Polynomial:** The determinant is central in the theory of eigenvalues. The characteristic polynomial of \\(A\\) is defined as \\(p_A(\lambda) = \det(A - \lambda I)\\), and its roots are the eigenvalues of \\(A\\).

- **Differential Equations:** In systems of linear differential equations, the Wronskian determinant is used to determine linear independence of solutions. The determinant also appears in the change of variables formula for multiple integrals (Jacobian determinant).

The determinant thus plays a fundamental role in linear algebra, geometry, and analysis, linking algebraic structure to geometric and analytic properties.
