# Linear Algebra

Linear algebra is the branch of mathematics concerned with the study of vector spaces, linear mappings between such spaces, and the algebraic structures arising from them. It provides the foundational language and tools for much of modern mathematics, science, and engineering.

## Vectors and Vector Spaces

A **vector** is an element of a vector space, typically denoted by a bold lowercase letter, such as \\(\mathbf{x}\\). A **vector space** \\(V\\) over a field \\(\mathbb{F}\\) (commonly \\(\mathbb{R}\\) or \\(\mathbb{C}\\)) is a set equipped with two operations:

- **Vector addition**: For \\(\mathbf{u}, \mathbf{v} \in V\\), the sum \\(\mathbf{u} + \mathbf{v}\\) is in \\(V\\).
- **Scalar multiplication**: For \\(\alpha \in \mathbb{F}\\), \\(\alpha \mathbf{v} \in V\\).

These operations satisfy axioms such as associativity, commutativity (of addition), distributivity, existence of additive identity and inverses, and compatibility with field multiplication.

A **basis** of \\(V\\) is a set of linearly independent vectors \\(\{\mathbf{v}_1, \ldots, \mathbf{v}_n\}\\) that span \\(V\\): every vector \\(\mathbf{x} \in V\\) can be written uniquely as
\\[
\mathbf{x} = a_1 \mathbf{v}_1 + a_2 \mathbf{v}_2 + \cdots + a_n \mathbf{v}_n, \quad a_i \in \mathbb{F}.
\\]
The **dimension** of \\(V\\), denoted \\(\dim(V)\\), is the number of vectors in any basis.

## Linear Transformations and Matrices

A **linear transformation** is a function \\(T: V \to W\\) between vector spaces such that for all \\(\mathbf{u}, \mathbf{v} \in V\\) and scalars \\(\alpha, \beta \in \mathbb{F}\\),
\\[
T(\alpha \mathbf{u} + \beta \mathbf{v}) = \alpha T(\mathbf{u}) + \beta T(\mathbf{v}).
\\]
Linear transformations can be represented by **matrices**. If \\(T: \mathbb{F}^n \to \mathbb{F}^m\\), then there exists a matrix \\(\mathbf{A} \in \mathbb{F}^{m \times n}\\) such that
\\[
T(\mathbf{x}) = \mathbf{A}\mathbf{x}
\\]
for all \\(\mathbf{x} \in \mathbb{F}^n\\).

Matrix operations such as addition, multiplication, and inversion correspond to algebraic operations on linear transformations.

## Determinants and Their Properties

The **determinant** is a scalar function \\(\det: \mathbb{F}^{n \times n} \to \mathbb{F}\\) that assigns to each square matrix \\(\mathbf{A}\\) a number \\(\det(\mathbf{A})\\). Key properties include:
- \\(\det(\mathbf{A}) = 0\\) if and only if \\(\mathbf{A}\\) is singular (not invertible).
- \\(\det(\mathbf{A}\mathbf{B}) = \det(\mathbf{A}) \det(\mathbf{B})\\) for any square matrices \\(\mathbf{A}, \mathbf{B}\\).
- \\(\det(\mathbf{A}^{\mathsf{T}}) = \det(\mathbf{A})\\).
- The determinant is multilinear and alternating in the rows (or columns).

Geometrically, \\(|\det(\mathbf{A})|\\) represents the scaling factor of the linear transformation \\(\mathbf{A}\\) on volumes in \\(\mathbb{F}^n\\).

## Eigenvalues, Eigenvectors, and Diagonalization

For a square matrix \\(\mathbf{A} \in \mathbb{F}^{n \times n}\\), a nonzero vector \\(\mathbf{x} \in \mathbb{F}^n\\) is an **eigenvector** of \\(\mathbf{A}\\) if there exists a scalar \\(\lambda \in \mathbb{F}\\) (the **eigenvalue**) such that
\\[
\mathbf{A}\mathbf{x} = \lambda \mathbf{x}.
\\]
The set of all \\(\lambda\\) for which this equation has a nontrivial solution is found by solving
\\[
\det(\mathbf{A} - \lambda \mathbf{I}) = 0,
\\]
where \\(\mathbf{I}\\) is the identity matrix.

If \\(\mathbf{A}\\) has \\(n\\) linearly independent eigenvectors, it can be **diagonalized**: there exists an invertible matrix \\(\mathbf{P}\\) such that
\\[
\mathbf{A} = \mathbf{P}\mathbf{D}\mathbf{P}^{-1},
\\]
where \\(\mathbf{D}\\) is diagonal with the eigenvalues of \\(\mathbf{A}\\) on its diagonal.

## Inner Product Spaces, Orthogonality, and Projections

An **inner product space** is a vector space \\(V\\) equipped with an inner product \\(\langle \cdot, \cdot \rangle: V \times V \to \mathbb{F}\\), satisfying linearity in the first argument, conjugate symmetry, and positive-definiteness. In \\(\mathbb{R}^n\\), the standard inner product is
\\[
\langle \mathbf{x}, \mathbf{y} \rangle = \mathbf{x}^{\mathsf{T}} \mathbf{y} = \sum_{i=1}^n x_i y_i.
\\]
Two vectors \\(\mathbf{x}, \mathbf{y}\\) are **orthogonal** if \\(\langle \mathbf{x}, \mathbf{y} \rangle = 0\\).

Given a subspace \\(W \subset V\\), the **orthogonal projection** of \\(\mathbf{x}\\) onto \\(W\\) is the unique vector \\(\mathbf{p} \in W\\) such that \\(\mathbf{x} - \mathbf{p}\\) is orthogonal to \\(W\\). Projections are fundamental in least squares approximation and many applications.

## Applications in Science and Engineering

Linear algebra underpins numerous fields:
- **Systems of equations**: Many scientific models reduce to solving \\(\mathbf{A}\mathbf{x} = \mathbf{b}\\). Existence and uniqueness depend on properties such as rank and invertibility.
- **Optimization**: Linear and quadratic programming, as well as more general optimization, rely on linear algebraic formulations.
- **Signal processing**: Concepts like the Fourier transform, principal component analysis (PCA), and filtering are grounded in linear algebra.
- **Computer graphics**: Transformations (rotation, scaling, translation) are performed using matrices, and 3D rendering relies on vector and matrix operations.

Linear algebra is thus a foundational tool for modeling, analyzing, and solving problems across mathematics, science, and engineering.