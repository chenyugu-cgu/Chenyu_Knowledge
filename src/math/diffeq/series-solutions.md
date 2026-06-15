# Series Solutions

When an ODE has variable coefficients and no elementary solution, we seek a solution as a **power series**. This approach generates the special functions of mathematical physics.

## Power Series Method

Near an **ordinary point** \\(x_0\\), assume
\\[
y(x) = \sum_{n=0}^{\infty} a_n (x - x_0)^n,
\\]
substitute into the ODE, and match powers of \\(x\\) to get a **recurrence relation** for the coefficients \\(a_n\\). The first two coefficients are set by the initial conditions.

## The Method of Frobenius

At a **regular singular point**, the plain power series fails; instead use
\\[
y(x) = x^r\sum_{n=0}^{\infty} a_n x^n,
\\]
where the exponent \\(r\\) solves the **indicial equation**. This handles equations like Bessel's that are singular at the origin.

## Special Functions

Series solutions of physically important equations define named functions:

| Equation | Solutions | Appears in |
|---|---|---|
| Bessel | \\(J_\nu, Y_\nu\\) | circular membranes, waveguides |
| Legendre | \\(P_n\\) | spherical problems, multipoles |
| Hermite | \\(H_n\\) | quantum harmonic oscillator |
| Laguerre | \\(L_n\\) | hydrogen atom |

These reappear constantly in [PDEs](pdes.md), [quantum mechanics](../../physics/modern/quantum.md), and [electromagnetism](../../physics/em/README.md).

## Convergence

The series converges within the distance to the nearest singularity of the coefficients in the complex plane (see [Complex Analysis](../complex/README.md)). Truncating gives an accurate local approximation.

## See Also

- [Series and Sequences](../calculus/series.md)
- [Partial Differential Equations](pdes.md)
- [Quantum Mechanics](../../physics/modern/quantum.md)
