# Contour Integration

Integration in the complex plane is taken along a **contour** (a path). The central theorems of Cauchy make these integrals astonishingly well-behaved for analytic functions.

## Cauchy's Integral Theorem

If \\(f\\) is analytic on and inside a simple closed contour \\(C\\), then
\\[
\oint_C f(z)\,dz = 0.
\\]
The integral of an analytic function around any closed loop is zero — path independence, the complex analogue of a conservative field.

## Cauchy's Integral Formula

For \\(f\\) analytic inside \\(C\\) and a point \\(z_0\\) enclosed by \\(C\\),
\\[
f(z_0) = \frac{1}{2\pi i}\oint_C \frac{f(z)}{z - z_0}\,dz,
\\]
and for derivatives,
\\[
f^{(n)}(z_0) = \frac{n!}{2\pi i}\oint_C \frac{f(z)}{(z - z_0)^{n+1}}\,dz.
\\]
A function's values on a boundary determine it (and all its derivatives) everywhere inside — a striking rigidity with no real-variable counterpart.

## Consequences

- **Analytic ⇒ infinitely differentiable**, and equal to its Taylor series (analytic functions are *entire-ly* determined locally).
- **Liouville's theorem** — a bounded entire function is constant; this proves the fundamental theorem of algebra.
- **Maximum modulus principle** — \\(|f|\\) attains its maximum on the boundary.

## Laurent Series

Around an isolated singularity, \\(f\\) expands in powers including negative ones:
\\[
f(z) = \sum_{n=-\infty}^{\infty} a_n (z - z_0)^n.
\\]
The coefficient \\(a_{-1}\\) is the **residue** — the key to the next chapter.

## See Also

- [Complex Functions](functions.md)
- [Residue Theorem](residues.md)
