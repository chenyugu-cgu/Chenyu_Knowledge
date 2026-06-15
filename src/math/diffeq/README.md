# Differential Equations

A **differential equation** relates a function to its derivatives. Because almost every physical law is stated as a rate of change — Newton's second law, the heat equation, circuit dynamics, population growth — differential equations are the native language of science and engineering.

## Classification

| Distinction | Meaning |
|---|---|
| ODE vs. PDE | one independent variable vs. several |
| Order | highest derivative present |
| Linear vs. nonlinear | linear in the unknown and its derivatives, or not |
| Homogeneous vs. forced | zero right-hand side, or driven by an input |
| IVP vs. BVP | conditions at one point (initial) vs. several (boundary) |

A general linear ODE of order \\(n\\):
\\[
a_n(x)\,y^{(n)} + \cdots + a_1(x)\,y' + a_0(x)\,y = g(x).
\\]
Its solution is the **homogeneous** (natural) solution plus a **particular** (forced) solution.

## Why It Matters

This group treats the **analytic** side — closed-form solution techniques — complementing the [Numerical Methods](../numerical/README.md) section, which solves equations that have no closed form. The two together cover almost everything you will meet in [dynamics](../../eng/dynamics/README.md), [control](../../eng/control/README.md), [heat transfer](../../eng/heat-transfer/README.md), and [signals](../../signals/fundamentals.md).

## Chapter Map

- [First-Order ODEs](first-order.md) — separable, linear, exact, applications.
- [Second-Order Linear ODEs](second-order.md) — constant coefficients, resonance.
- [Systems of ODEs](systems.md) — matrix methods, phase portraits.
- [Laplace Transform Methods](laplace-method.md) — algebraic solution of IVPs.
- [Series Solutions](series-solutions.md) — power series, special functions.
- [Partial Differential Equations](pdes.md) — heat, wave, Laplace; separation of variables.

## See Also

- [Laplace Transform](../../signals/laplace-transform.md)
- [Eigenvalues and Eigenvectors](../linear-algebra/eigen.md)
