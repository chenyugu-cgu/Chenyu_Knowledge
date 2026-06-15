# Combinatorics

Combinatorics is the art of counting — how many ways can something happen? It underlies [probability](../probability/axioms.md), algorithm analysis, and coding theory.

## The Basic Counting Rules

- **Product rule:** if a task splits into independent stages with \\(n_1, n_2, \dots\\) choices, the total is \\(n_1 \cdot n_2 \cdots\\).
- **Sum rule:** mutually exclusive alternatives add.
- **Inclusion–exclusion:** \\(|A\cup B| = |A| + |B| - |A\cap B|\\), extended to more sets with alternating signs.

## Permutations and Combinations

| Quantity | Formula | Meaning |
|---|---|---|
| Permutations | \\(P(n,k) = \dfrac{n!}{(n-k)!}\\) | ordered selections |
| Combinations | \\(\binom{n}{k} = \dfrac{n!}{k!(n-k)!}\\) | unordered selections |

Order matters for permutations, not for combinations.

## The Binomial Theorem

\\[
(x + y)^n = \sum_{k=0}^{n}\binom{n}{k} x^{k} y^{n-k}.
\\]
The coefficients form **Pascal's triangle**, with the identity \\(\binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}\\).

## The Pigeonhole Principle

If \\(n\\) items go into \\(m < n\\) boxes, some box holds at least two. Despite its simplicity, it proves surprising existence results (e.g. two people in a large city share the same number of hairs).

## Counting with Repetition

- Selections with repetition: \\(\binom{n+k-1}{k}\\) ("stars and bars").
- Arrangements of multisets: \\(\dfrac{n!}{n_1!\,n_2!\cdots}\\).

## Applications

- **Probability** — equally likely outcomes are counted combinatorially (see [Axioms of Probability](../probability/axioms.md)).
- **Algorithm analysis** — counting operations and configurations.
- **Coding theory** — counting codewords and error patterns ([Information Theory](../../cs/information-theory/README.md)).

## See Also

- [Logic and Proofs](logic-proofs.md)
- [Axioms of Probability](../probability/axioms.md)
- [Distributions](../probability/distributions.md) — the binomial distribution.
