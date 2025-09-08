# Eigenvalues and Eigenvectors

Eigenvalues and eigenvectors are fundamental concepts in linear algebra that reveal intrinsic properties of linear transformations represented by matrices.

## Definition

Given a square matrix \\(\mathbf{A} \in \mathbb{C}^{n \times n}\\), an eigenvector \\(\mathbf{v} \in \mathbb{C}^n\\) (nonzero vector) and a scalar \\(\lambda \in \mathbb{C}\\) satisfy the eigenvalue equation

\\[
\mathbf{A} \mathbf{v} = \lambda \mathbf{v}.
\\]

Here, \\(\lambda\\) is called an **eigenvalue** of \\(\mathbf{A}\\), and \\(\mathbf{v}\\) is the corresponding **eigenvector**. This equation states that the action of \\(\mathbf{A}\\) on \\(\mathbf{v}\\) results in a vector collinear with \\(\mathbf{v}\\), scaled by \\(\lambda\\).

## Characteristic Polynomial

Rearranging the eigenvalue equation yields

\\[
(\mathbf{A} - \lambda \mathbf{I}) \mathbf{v} = \mathbf{0},
\\]

where \\(\mathbf{I}\\) is the identity matrix. For nontrivial solutions \\(\mathbf{v} \neq \mathbf{0}\\) to exist, the matrix \\(\mathbf{A} - \lambda \mathbf{I}\\) must be singular, implying

\\[
\det(\mathbf{A} - \lambda \mathbf{I}) = 0.
\\]

This determinant is a polynomial in \\(\lambda\\) of degree \\(n\\), called the **characteristic polynomial** of \\(\mathbf{A}\\). Its roots are the eigenvalues of \\(\mathbf{A}\\).

## Properties of Eigenvalues

### Algebraic Multiplicity

The **algebraic multiplicity** of an eigenvalue \\(\lambda\\) is its multiplicity as a root of the characteristic polynomial.

### Geometric Multiplicity

The **geometric multiplicity** of \\(\lambda\\) is the dimension of the null space (kernel) of \\(\mathbf{A} - \lambda \mathbf{I}\\), i.e., the number of linearly independent eigenvectors associated with \\(\lambda\\).

It always holds that

\\[
1 \leq \text{geometric multiplicity} \leq \text{algebraic multiplicity}.
\\]

## Diagonalization

A matrix \\(\mathbf{A}\\) is **diagonalizable** if it is similar to a diagonal matrix \\(\mathbf{D}\\):

\\[
\mathbf{A} = \mathbf{P} \mathbf{D} \mathbf{P}^{-1},
\\]

where \\(\mathbf{D}\\) is diagonal with eigenvalues on the diagonal, and \\(\mathbf{P}\\) is invertible with columns formed by eigenvectors of \\(\mathbf{A}\\).

Diagonalizability requires that the sum of geometric multiplicities equals \\(n\\), i.e., \\(\mathbf{A}\\) has a complete basis of eigenvectors.

## Special Classes of Matrices

### Symmetric Matrices

A matrix \\(\mathbf{A} \in \mathbb{R}^{n \times n}\\) is **symmetric** if \\(\mathbf{A} = \mathbf{A}^T\\). Symmetric matrices have real eigenvalues and are diagonalizable by an orthogonal matrix:

\\[
\mathbf{A} = \mathbf{Q} \mathbf{\Lambda} \mathbf{Q}^T,
\\]

where \\(\mathbf{Q}\\) is orthogonal (\\(\mathbf{Q}^T = \mathbf{Q}^{-1}\\)) and \\(\mathbf{\Lambda}\\) is diagonal with real eigenvalues.

### Orthogonal Matrices

A matrix \\(\mathbf{Q}\\) is **orthogonal** if \\(\mathbf{Q}^T \mathbf{Q} = \mathbf{I}\\). Its eigenvalues satisfy \\(|\lambda| = 1\\), and it represents isometries (distance-preserving transformations).

### Hermitian Matrices

For complex matrices, \\(\mathbf{A} \in \mathbb{C}^{n \times n}\\) is **Hermitian** if \\(\mathbf{A} = \mathbf{A}^\dagger\\), where \\(\mathbf{A}^\dagger\\) is the conjugate transpose. Hermitian matrices have real eigenvalues and are diagonalizable by a unitary matrix:

\\[
\mathbf{A} = \mathbf{U} \mathbf{\Lambda} \mathbf{U}^\dagger,
\\]

where \\(\mathbf{U}\\) is unitary (\\(\mathbf{U}^\dagger = \mathbf{U}^{-1}\\)).

### Unitary Matrices

A matrix \\(\mathbf{U} \in \mathbb{C}^{n \times n}\\) is **unitary** if \\(\mathbf{U}^\dagger \mathbf{U} = \mathbf{I}\\). Eigenvalues of unitary matrices lie on the unit circle (\\(|\lambda| = 1\\)).

## Spectral Theorem

The spectral theorem states that any normal matrix \\(\mathbf{A}\\) (i.e., \\(\mathbf{A} \mathbf{A}^\dagger = \mathbf{A}^\dagger \mathbf{A}\\)) can be diagonalized by a unitary matrix:

\\[
\mathbf{A} = \mathbf{U} \mathbf{\Lambda} \mathbf{U}^\dagger,
\\]

where \\(\mathbf{\Lambda}\\) is diagonal with eigenvalues of \\(\mathbf{A}\\). This generalizes the diagonalization of symmetric and Hermitian matrices and ensures a basis of orthonormal eigenvectors.

## Applications

- **Differential Equations:** Eigenvalues characterize stability and solution behavior of linear systems \\(\dot{\mathbf{x}} = \mathbf{A} \mathbf{x}\\). Eigenvectors provide modes of the system.

- **Stability Analysis:** The sign of eigenvalues' real parts determines equilibrium stability in dynamical systems.

- **Quantum Mechanics:** Observables are represented by Hermitian operators; eigenvalues correspond to measurable quantities, eigenvectors to quantum states.

- **Principal Component Analysis (PCA):** Eigenvectors of covariance matrices define principal components; eigenvalues indicate variance explained by each component.
