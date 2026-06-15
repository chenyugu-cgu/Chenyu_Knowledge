# Complex Analysis

Complex analysis studies functions of a complex variable \\(z = x + iy\\). Remarkably, the requirement that a function be differentiable in the complex sense is so strong that it forces deep structure — and yields powerful tools used throughout signals, control, and physics.

## Why Engineers Need It

- **Signals and control** — poles and zeros live in the complex \\(s\\)- and \\(z\\)-planes; stability is a statement about complex roots. See [Laplace Transform](../../signals/laplace-transform.md), [Stability Analysis](../../eng/control/stability.md).
- **AC circuits** — phasors are complex numbers; impedance is complex. See [AC and DC Analysis](../../eng/electrical/ac-dc.md).
- **Fluid and EM fields** — 2-D potential flow and electrostatics use complex potentials.
- **Integrals** — the residue theorem evaluates real integrals that resist ordinary calculus.

## Chapter Map

- [Complex Functions](functions.md) — analyticity, the Cauchy–Riemann equations.
- [Contour Integration](contour-integration.md) — Cauchy's theorem and integral formula.
- [Residue Theorem](residues.md) — evaluating integrals via poles.

## The Complex Plane

A complex number has rectangular form \\(z = x + iy\\) and polar form \\(z = re^{i\theta}\\), with \\(r = |z|\\) and \\(\theta = \arg z\\). **Euler's formula** \\(e^{i\theta} = \cos\theta + i\sin\theta\\) ties exponentials to rotations — the single most useful identity in engineering mathematics.

## See Also

- [Complex Numbers in Linear Algebra](../linear-algebra/eigen.md)
- [Fourier Transform](../../signals/fourier-transform.md)
