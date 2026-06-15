# Floating-Point and Error

Computers represent real numbers with finite precision. Understanding the resulting errors is essential — ignoring them produces results that are confidently wrong.

## Floating-Point Representation

The IEEE 754 standard stores a number as sign, exponent, and mantissa:
\\[
x = \pm\, m \times 2^{e}.
\\]
Double precision (64-bit) has ~15–16 significant decimal digits; the gap between 1 and the next representable number is **machine epsilon** \\(\varepsilon \approx 2.2\times10^{-16}\\).

## Sources of Error

- **Round-off** — each operation rounds to the nearest representable value.
- **Truncation** — approximating an infinite process (series, derivative) by a finite one.
- **Catastrophic cancellation** — subtracting nearly equal numbers loses significant digits (e.g. the naive quadratic formula).

## Conditioning and Stability

- **Conditioning** is a property of the *problem*: a well-conditioned problem has solutions insensitive to input perturbations. The **condition number** \\(\kappa\\) quantifies this (for linear systems, \\(\kappa(A) = \|A\|\|A^{-1}\|\\)).
- **Stability** is a property of the *algorithm*: a stable algorithm does not amplify error beyond what conditioning dictates.

A well-conditioned problem solved by a stable algorithm gives accurate results; either failing can ruin the answer.

## Practical Guidance

- Compare floats with a tolerance, never `==`.
- Reformulate to avoid cancellation (e.g. the numerically stable quadratic formula).
- Prefer algorithms with proven stability (pivoting in [linear solves](linear-systems.md)).
- Sum many numbers carefully (Kahan summation) when precision matters.
- Track relative error \\(|\hat{x}-x|/|x|\\), not just absolute.

## Why It Bites

Naively summing a long series, inverting an ill-conditioned matrix, or differencing close measurements can produce garbage despite correct math. Numerical awareness separates working simulations from mysterious failures.

## See Also

- [Performance and Parallelism](performance.md)
- [Solving Linear Systems](linear-systems.md)
- [Root Finding](../../math/numerical/root-finding.md)
