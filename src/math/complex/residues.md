# Residue Theorem

The residue theorem is the crown jewel of complex analysis: it reduces a contour integral to a sum of simple local quantities at the enclosed singularities — and evaluates many real integrals that elementary calculus cannot.

## The Theorem

If \\(f\\) is analytic inside a closed contour \\(C\\) except at isolated singularities \\(z_k\\), then
\\[
\oint_C f(z)\,dz = 2\pi i \sum_k \operatorname{Res}(f, z_k).
\\]

## Computing Residues

For a **simple pole** at \\(z_0\\):
\\[
\operatorname{Res}(f, z_0) = \lim_{z\to z_0}(z - z_0)f(z).
\\]
For a **pole of order \\(m\\)**:
\\[
\operatorname{Res}(f, z_0) = \frac{1}{(m-1)!}\lim_{z\to z_0}\frac{d^{m-1}}{dz^{m-1}}\big[(z-z_0)^m f(z)\big].
\\]

## Evaluating Real Integrals

The technique: close the real line with a large semicircular arc, count the residues of the poles enclosed, and (when the arc contributes nothing) read off the real integral.

**Example.**
\\[
\int_{-\infty}^{\infty}\frac{dx}{x^2 + 1} = 2\pi i\,\operatorname{Res}\!\left(\frac{1}{z^2+1}, i\right) = 2\pi i\cdot\frac{1}{2i} = \pi.
\\]

## Engineering Use

- **Inverse Laplace and Z transforms** are computed by summing residues (the Bromwich integral) — directly relevant to [control](../../eng/control/transfer.md) and [signals](../../signals/laplace-transform.md).
- **Fourier integrals** of rational functions yield to residues.
- **Stability** — counting poles in a region (the argument principle, behind the [Nyquist criterion](../../eng/control/stability.md)) is a residue computation.

## The Argument Principle

\\[
\frac{1}{2\pi i}\oint_C \frac{f'(z)}{f(z)}\,dz = Z - P,
\\]
the number of zeros minus poles inside \\(C\\) — the mathematical heart of the Nyquist stability test.

## See Also

- [Contour Integration](contour-integration.md)
- [Stability Analysis](../../eng/control/stability.md)
- [Laplace Transform](../../signals/laplace-transform.md)
