# Complex Functions

A complex function \\(f(z) = u(x,y) + i\,v(x,y)\\) maps the complex plane to itself. The central concept is **analyticity** (complex differentiability), which is far more restrictive — and powerful — than real differentiability.

## The Cauchy–Riemann Equations

\\(f\\) is **analytic** (holomorphic) at a point if it is complex-differentiable in a neighborhood. This holds iff the real and imaginary parts satisfy the **Cauchy–Riemann equations**:
\\[
\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y}, \qquad
\frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}.
\\]
A consequence: both \\(u\\) and \\(v\\) are **harmonic** (\\(\nabla^2 u = 0\\)) — which is why complex analysis solves 2-D potential problems in electrostatics and fluid flow.

## Elementary Functions

- **Exponential:** \\(e^{z} = e^{x}(\cos y + i\sin y)\\) — periodic with period \\(2\pi i\\).
- **Trigonometric:** \\(\cos z = \frac{e^{iz}+e^{-iz}}{2}\\), \\(\sin z = \frac{e^{iz}-e^{-iz}}{2i}\\).
- **Logarithm:** \\(\ln z = \ln|z| + i\arg z\\) — multivalued, requiring a branch cut.

## Singularities

Points where \\(f\\) fails to be analytic:
- **Removable** — \\(f\\) can be redefined to be analytic.
- **Pole of order \\(m\\)** — \\(f\\) blows up like \\(1/(z-z_0)^m\\); these are the poles of transfer functions.
- **Essential** — wild behavior (e.g. \\(e^{1/z}\\) at 0).

## Conformal Mapping

Analytic functions with \\(f'\neq0\\) are **conformal** — they preserve angles locally. Conformal maps transform hard geometries into simple ones, used in airfoil design (Joukowski transform), electrostatics, and heat conduction.

## Connection to Engineering

The poles and zeros that dominate [control](../../eng/control/transfer.md) and [signal](../../signals/laplace-transform.md) analysis are exactly the singularities and roots of complex functions. Frequency response is \\(f\\) evaluated on the imaginary axis.

## See Also

- [Contour Integration](contour-integration.md)
- [Vector Calculus](../calculus/vector.md) — harmonic functions and potentials.
