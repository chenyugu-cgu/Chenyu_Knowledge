# Logic and Proofs

Logic is the grammar of mathematics. Proofs are how we establish truth with certainty — the discipline behind correct algorithms and verified systems.

## Propositional Logic

A **proposition** is a statement that is true or false. Connectives combine them:

| Connective | Symbol | Meaning |
|---|---|---|
| Negation | \\(\neg p\\) | not \\(p\\) |
| Conjunction | \\(p \wedge q\\) | \\(p\\) and \\(q\\) |
| Disjunction | \\(p \vee q\\) | \\(p\\) or \\(q\\) |
| Implication | \\(p \Rightarrow q\\) | if \\(p\\) then \\(q\\) |
| Biconditional | \\(p \Leftrightarrow q\\) | \\(p\\) iff \\(q\\) |

Key equivalences: De Morgan's laws \\(\neg(p\wedge q) \equiv \neg p \vee \neg q\\); the contrapositive \\(p\Rightarrow q \equiv \neg q \Rightarrow \neg p\\) (logically equivalent — the basis of proof by contrapositive).

## Predicate Logic and Quantifiers

Predicates depend on variables; quantifiers bind them:
\\[
\forall x\, P(x)\ (\text{for all}), \qquad \exists x\, P(x)\ (\text{there exists}).
\\]
Negation flips them: \\(\neg\forall x\,P(x) \equiv \exists x\,\neg P(x)\\).

## Proof Techniques

- **Direct proof** — assume the hypothesis, derive the conclusion.
- **Contrapositive** — prove \\(\neg q \Rightarrow \neg p\\).
- **Contradiction** — assume the negation and derive an absurdity (e.g. \\(\sqrt2\\) is irrational).
- **Induction** — prove a base case \\(P(1)\\), then \\(P(n)\Rightarrow P(n+1)\\); valid for all naturals. **Strong induction** assumes all cases up to \\(n\\).
- **Construction / counterexample** — exhibit an object, or disprove with one instance.

## Worked Example: Induction

Prove \\(\sum_{k=1}^{n} k = \dfrac{n(n+1)}{2}\\). Base: \\(n=1\\) gives 1. Step: assume true for \\(n\\); then \\(\sum_{k=1}^{n+1} k = \frac{n(n+1)}{2} + (n+1) = \frac{(n+1)(n+2)}{2}\\). ∎

## Boolean Algebra

Propositional logic is isomorphic to Boolean algebra, the foundation of [digital logic](../../eng/electrical/digital.md) and circuit design.

## See Also

- [Combinatorics](combinatorics.md)
- [Digital Logic](../../eng/electrical/digital.md)
- [Complexity and Analysis](../../cs/algorithms/complexity.md)
