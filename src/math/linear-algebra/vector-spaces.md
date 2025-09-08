
# Vector Spaces

## Definition

A **vector space** (or **linear space**) over a field \\( F \\) is a set \\( V \\) equipped with two operations:

1. **Vector addition:** An operation \\( + : V \times V \to V \\) such that for any \\( u, v \in V \\), \\( u + v \in V \\).
2. **Scalar multiplication:** An operation \\( \cdot : F \times V \to V \\) such that for any \\( a \in F \\) and \\( v \in V \\), \\( a \cdot v \in V \\).

These operations must satisfy the following axioms for all \\( u, v, w \in V \\) and all scalars \\( a, b \in F \\):

1. **Associativity of addition:** \\( (u + v) + w = u + (v + w) \\)
2. **Commutativity of addition:** \\( u + v = v + u \\)
3. **Additive identity:** There exists \\( 0 \in V \\) such that \\( v + 0 = v \\) for all \\( v \in V \\).
4. **Additive inverse:** For every \\( v \in V \\), there exists \\( -v \in V \\) such that \\( v + (-v) = 0 \\).
5. **Compatibility of scalar multiplication with field multiplication:** \\( a \cdot (b \cdot v) = (ab) \cdot v \\)
6. **Identity element of scalar multiplication:** \\( 1 \cdot v = v \\), where \\( 1 \\) is the multiplicative identity in \\( F \\).
7. **Distributivity of scalar multiplication with respect to vector addition:** \\( a \cdot (u + v) = a \cdot u + a \cdot v \\)
8. **Distributivity of scalar multiplication with respect to field addition:** \\( (a + b) \cdot v = a \cdot v + b \cdot v \\)

## Subspaces

A **subspace** of a vector space \\( V \\) is a subset \\( W \subseteq V \\) that is itself a vector space under the operations of \\( V \\). That is, \\( W \\) is closed under addition and scalar multiplication, contains the zero vector, and satisfies all vector space axioms.

## Span and Linear Combinations

Given a subset \\( S \subseteq V \\), the **span** of \\( S \\), denoted \\( \operatorname{span}(S) \\), is the set of all finite linear combinations of elements of \\( S \\):
\\[
  \operatorname{span}(S) = \left\\{ \sum_{i=1}^n a_i v_i \mid n \in \mathbb{N},\ v_i \in S,\ a_i \in F \right\\}
\\]
A **linear combination** of vectors \\( v_1, \ldots, v_n \\) with scalars \\( a_1, \ldots, a_n \\) is any vector of the form \\( a_1 v_1 + \cdots + a_n v_n \\).

## Linear Independence

A set of vectors \\( \{v_1, \ldots, v_n\} \subseteq V \\) is **linearly independent** if the only solution to
\\[
  a_1 v_1 + \cdots + a_n v_n = 0
\\]
is \\( a_1 = a_2 = \cdots = a_n = 0 \\). Otherwise, the set is **linearly dependent**.

## Basis and Dimension

A **basis** of a vector space \\( V \\) is a linearly independent set of vectors that spans \\( V \\). Every vector in \\( V \\) can be written uniquely as a linear combination of basis vectors.

The **dimension** of \\( V \\), denoted \\( \dim V \\), is the cardinality (number of elements) of any basis of \\( V \\). All bases of a finite-dimensional vector space have the same number of elements.

## Examples of Vector Spaces

- **Euclidean space:** \\( \mathbb{R}^n \\) is the set of all \\( n \\)-tuples of real numbers, with componentwise addition and scalar multiplication.
- **Polynomial spaces:** The set \\( P_n(F) \\) of all polynomials of degree at most \\( n \\) over a field \\( F \\) is a vector space.
- **Function spaces:** The set of all functions from a set \\( X \\) to a field \\( F \\), denoted \\( F^X \\), is a vector space under pointwise operations.

## Coordinates Relative to a Basis

Given a basis \\( \{e_1, \ldots, e_n\} \\) of \\( V \\), every \\( v \in V \\) can be uniquely written as \\( v = a_1 e_1 + \cdots + a_n e_n \\) for scalars \\( a_i \in F \\). The tuple \\( (a_1, \ldots, a_n) \\) is called the **coordinate vector** of \\( v \\) with respect to the basis.

## Direct Sums

If \\( U \\) and \\( W \\) are subspaces of \\( V \\) such that every \\( v \in V \\) can be written uniquely as \\( v = u + w \\) with \\( u \in U \\), \\( w \in W \\), then \\( V \\) is the **direct sum** of \\( U \\) and \\( W \\), denoted \\( V = U \oplus W \\).

## Quotient Spaces

Given a vector space \\( V \\) and a subspace \\( W \\), the **quotient space** \\( V / W \\) is the set of equivalence classes \\( v + W = \{ v + w \mid w \in W \} \\), with vector space operations defined naturally. The dimension satisfies \\( \dim(V / W) = \dim V - \dim W \\) if \\( V \\) is finite-dimensional.

## Dual Spaces and Linear Functionals

The **dual space** \\( V^* \\) of a vector space \\( V \\) is the set of all linear functionals \\( f: V \to F \\), that is, all linear maps from \\( V \\) to its field \\( F \\). The dual space itself is a vector space, and if \\( V \\) is finite-dimensional, \\( \dim V^* = \dim V \\).

## Importance of Vector Spaces

Vector spaces are fundamental structures in mathematics. They provide the setting for linear algebra, underpinning areas such as geometry, analysis, quantum mechanics, and engineering. Concepts such as eigenvalues, eigenvectors, linear transformations, and inner product spaces are all grounded in the theory of vector spaces. Their abstraction allows for unifying diverse mathematical objects and facilitates the study of systems governed by linearity.
