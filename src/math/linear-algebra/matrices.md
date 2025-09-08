
# Matrix Operations

## Definition of a Matrix and Notation

A **matrix** is a rectangular array of numbers (or, more generally, elements from a field such as \\(\mathbb{R}\\) or \\(\mathbb{C}\\)), arranged in rows and columns. An \\(m \times n\\) matrix has \\(m\\) rows and \\(n\\) columns. The general form is:
\\[
A = \begin{bmatrix}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    a_{21} & a_{22} & \cdots & a_{2n} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}
\\]
where \\(a_{ij}\\) denotes the entry in the \\(i\\)-th row and \\(j\\)-th column.

## Matrix Addition and Scalar Multiplication

Given two matrices \\(A, B\\) of the same size \\(m \times n\\), their sum is defined entrywise:
\\[
(A + B)_{ij} = a_{ij} + b_{ij}
\\]
For a scalar \\(\alpha\\) and a matrix \\(A\\), the scalar multiple is:
\\[
(\alpha A)_{ij} = \alpha a_{ij}
\\]
These operations satisfy:
- **Commutativity**: \\(A + B = B + A\\).
- **Associativity**: \\((A + B) + C = A + (B + C)\\).
- **Distributivity**: \\(\alpha (A + B) = \alpha A + \alpha B\\), and \\((\alpha + \beta)A = \alpha A + \beta A\\).

## Matrix Multiplication

Let \\(A\\) be an \\(m \times n\\) matrix and \\(B\\) an \\(n \times p\\) matrix. The product \\(C = AB\\) is an \\(m \times p\\) matrix, defined by:
\\[
c_{ij} = \sum_{k=1}^{n} a_{ik} b_{kj}
\\]
Matrix multiplication is:
- **Associative**: \\(A(BC) = (AB)C\\).
- **Distributive**: \\(A(B + C) = AB + AC\\), \\((A + B)C = AC + BC\\).
- **Not commutative in general**: \\(AB \ne BA\\) in most cases.

## Transpose and Conjugate Transpose (Hermitian)

The **transpose** of an \\(m \times n\\) matrix \\(A\\), denoted \\(A^{\mathrm{T}}\\), is the \\(n \times m\\) matrix whose \\(i\\)-th row is the \\(i\\)-th column of \\(A\\):
\\[
(A^{\mathrm{T}})_{ij} = a_{ji}
\\]
For a matrix \\(A\\) with complex entries, the **conjugate transpose** (or **Hermitian adjoint**), denoted \\(A^{*}\\) or \\(A^{\dagger}\\), is defined as:
\\[
(A^{*})_{ij} = \overline{a_{ji}}
\\]
where \\(\overline{a_{ji}}\\) is the complex conjugate of \\(a_{ji}\\).

## Inverse of a Matrix

A square matrix \\(A \in \mathbb{F}^{n \times n}\\) is **invertible** (or **nonsingular**) if there exists a matrix \\(B\\) such that:
\\[
AB = BA = I_n
\\]
where \\(I_n\\) is the \\(n \times n\\) identity matrix. The inverse, if it exists, is unique and denoted \\(A^{-1}\\). A matrix is invertible if and only if its determinant is nonzero (see below).

## Determinant and Invertibility

The **determinant** is a scalar function defined on square matrices, denoted \\(\det(A)\\) or \\(|A|\\). For \\(A \in \mathbb{F}^{n \times n}\\):
\\[
A \text{ is invertible} \iff \det(A) \ne 0
\\]
The determinant encodes geometric properties such as volume scaling under the associated linear transformation.

## Rank of a Matrix and Linear Systems

The **rank** of a matrix \\(A\\), denoted \\(\operatorname{rank}(A)\\), is the dimension of the column space (or row space) of \\(A\\). It equals the maximal number of linearly independent columns (or rows). The rank determines:
- The maximal number of linearly independent equations in the linear system \\(Ax = b\\).
- The solvability of \\(Ax = b\\): the system has a solution for every \\(b\\) if and only if \\(A\\) has full rank (for square \\(A\\), this means \\(\operatorname{rank}(A) = n\\)).

## Special Classes of Matrices

- **Diagonal matrix**: All off-diagonal entries are zero, i.e., \\(a_{ij} = 0\\) for \\(i \ne j\\).
- **Triangular matrix**: All entries either above (upper triangular) or below (lower triangular) the main diagonal are zero.
- **Symmetric matrix**: \\(A^{\mathrm{T}} = A\\), i.e., \\(a_{ij} = a_{ji}\\) for all \\(i, j\\).
- **Orthogonal matrix**: Real square matrix \\(Q\\) such that \\(Q^{\mathrm{T}} Q = I\\). The columns (and rows) form an orthonormal set.
- **Unitary matrix**: Complex square matrix \\(U\\) such that \\(U^{*} U = I\\). The columns (and rows) form an orthonormal set under the complex inner product.

## Matrices as Linear Transformations

Every matrix \\(A \in \mathbb{F}^{m \times n}\\) represents a linear transformation \\(T: \mathbb{F}^n \to \mathbb{F}^m\\), defined by \\(T(x) = Ax\\). The properties of matrices—such as invertibility, rank, symmetry, and orthogonality—correspond to fundamental properties of the associated linear transformations (e.g., invertibility, injectivity, preservation of inner products).
