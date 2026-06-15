# Z-Transform

The Z-transform is to discrete-time systems what the Laplace transform is to continuous-time systems. It converts difference equations into algebraic equations and provides the tool for analyzing digital filters and sampled-data control.

## Definition

The (bilateral) Z-transform of a sequence \\(x[n]\\) is
\\[
X(z) = \sum_{n=-\infty}^{\infty} x[n]\, z^{-n},
\\]
defined on its **region of convergence (ROC)**, an annulus \\(r_1 < |z| < r_2\\) in the complex plane. The unilateral version sums from \\(n=0\\) and is used with initial conditions.

## Relationship to the Laplace Transform

Sampling at period \\(T_s\\) maps the \\(s\\)-plane to the \\(z\\)-plane via \\(z = e^{sT_s}\\). The left half \\(s\\)-plane (stability region) maps to the **interior of the unit circle** \\(|z| < 1\\), and the \\(j\omega\\)-axis maps to the unit circle \\(|z|=1\\).

## Key Properties

| Property | \\(x[n]\\) | \\(X(z)\\) |
|---|---|---|
| Linearity | \\(a x_1 + b x_2\\) | \\(a X_1 + b X_2\\) |
| Time shift | \\(x[n-k]\\) | \\(z^{-k}X(z)\\) |
| Convolution | \\(x*h\\) | \\(X(z)H(z)\\) |
| Scaling | \\(a^n x[n]\\) | \\(X(z/a)\\) |
| Differencing | \\(x[n]-x[n-1]\\) | \\((1-z^{-1})X(z)\\) |

## Common Transform Pairs

\\[
\delta[n]\leftrightarrow 1,\quad
u[n]\leftrightarrow \frac{1}{1-z^{-1}}\ (|z|>1),\quad
a^n u[n]\leftrightarrow \frac{1}{1-a z^{-1}}\ (|z|>|a|).
\\]

## Digital Filters and the Transfer Function

A linear constant-coefficient difference equation
\\[
\sum_{k=0}^{N} a_k\, y[n-k] = \sum_{m=0}^{M} b_m\, x[n-m]
\\]
has transfer function
\\[
H(z) = \frac{\sum_{m} b_m z^{-m}}{\sum_{k} a_k z^{-k}}.
\\]
An **FIR** filter has only numerator terms (always stable, linear phase possible); an **IIR** filter has poles and can be unstable but is more efficient.

## Stability Criterion

A causal discrete LTI system is **BIBO stable** if and only if all poles of \\(H(z)\\) lie strictly inside the unit circle, i.e. \\(|z_p| < 1\\) for every pole \\(z_p\\).

## Worked Example: Difference Equation

For \\(y[n] = 0.5\,y[n-1] + x[n]\\), transform to \\(Y(z) = 0.5 z^{-1}Y(z) + X(z)\\), giving
\\[
H(z) = \frac{1}{1 - 0.5 z^{-1}}, \quad h[n] = (0.5)^n u[n].
\\]
The single pole at \\(z = 0.5\\) is inside the unit circle, so the filter is stable.

## See Also

- [Laplace Transform](laplace-transform.md)
- [Sampling and Reconstruction](sampling.md)
- [Digital Logic](../eng/electrical/digital.md)
