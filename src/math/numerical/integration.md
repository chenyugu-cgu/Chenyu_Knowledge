# Numerical Integration

Numerical integration, also known as numerical quadrature, refers to a collection of algorithms for approximating the definite integral of a function. Given a function \\( f(x) \\) defined on an interval \\( [a, b] \\), the goal is to approximate the integral

\\[
I = \int_{a}^{b} f(x) \, dx.
\\]

This task arises frequently in applied mathematics, physics, engineering, and computational science, especially when the integral cannot be evaluated analytically or the integrand is known only at discrete points.

## Sources of Error in Numerical Integration

Two primary sources of error affect numerical integration methods:

1. **Truncation Error:** This error arises from approximating the integral by a finite sum or polynomial approximation of the integrand. It depends on the smoothness of \\( f \\), the method used, and the number of evaluation points.

2. **Round-off Error:** Due to finite precision arithmetic in computers, round-off error accumulates when performing arithmetic operations. Although generally smaller than truncation error, for very fine discretizations or ill-conditioned problems it can become significant.

Balancing these errors is crucial for designing effective numerical integration schemes.

## Newton–Cotes Formulas

Newton–Cotes formulas approximate the integral by interpolating the integrand \\( f \\) with a polynomial passing through equally spaced points on \\( [a, b] \\), then integrating this polynomial exactly. Let \\( n+1 \\) equally spaced nodes be

\\[
x_i = a + i h, \quad h = \frac{b - a}{n}, \quad i = 0, 1, \ldots, n.
\\]

The integral is approximated by

\\[
I \approx \int_{a}^{b} P_n(x) \, dx = \sum_{i=0}^{n} w_i f(x_i),
\\]

where \\( P_n(x) \\) is the interpolating polynomial of degree \\( n \\) and \\( w_i \\) are weights derived from integrating the Lagrange basis polynomials.

### Common Newton–Cotes Rules

- **Rectangle Rule (Left or Right):** \\( n = 0 \\), uses a constant approximation. For example, the left rectangle rule is

\\[
I \approx h f(a).
\\]

- **Trapezoidal Rule:** \\( n = 1 \\), linear interpolation between two points:

\\[
I \approx \frac{h}{2} \left( f(a) + f(b) \right).
\\]

- **Simpson’s Rule:** \\( n = 2 \\), quadratic interpolation at three points:

\\[
I \approx \frac{h}{3} \left( f(a) + 4 f\left(a + h\right) + f(b) \right).
\\]

- **Higher-Order Newton–Cotes Rules:** Use polynomials of degree \\( n > 2 \\) with more nodes, but these can suffer from Runge’s phenomenon and numerical instability for large \\( n \\).

### Error Analysis of Newton–Cotes Formulas

The error in Newton–Cotes formulas can be expressed via the remainder term of polynomial interpolation. For sufficiently smooth \\( f \\), the error for the composite trapezoidal rule over \\( m \\) subintervals is

\\[
E_{\text{trap}} = -\frac{(b - a)^3}{12 m^2} f^{\prime\prime}(\xi),
\\]

for some \\( \xi \in [a, b] \\). This indicates the trapezoidal rule is second-order accurate, i.e., error decreases like \\( h^2 \\).

Simpson’s rule has error

\\[
E_{\text{Simpson}} = -\frac{(b - a)^5}{180 m^4} f^{(4)}(\eta),
\\]

for some \\( \eta \in [a, b] \\), showing fourth-order accuracy.

Higher-order Newton–Cotes formulas have errors involving higher derivatives but often suffer from numerical instability and oscillations.

## Gaussian Quadrature

Gaussian quadrature methods select both nodes \\( x_i \\) and weights \\( w_i \\) optimally to maximize the degree of exactness for polynomial integrands. Unlike Newton–Cotes, nodes are not equally spaced.

Given a weight function \\( w(x) \\) on \\( [a, b] \\), Gaussian quadrature approximates

\\[
I = \int_a^b f(x) w(x) \, dx \approx \sum_{i=1}^n w_i f(x_i),
\\]

where \\( \{x_i\} \\) are the roots of orthogonal polynomials associated with \\( w(x) \\).

### Orthogonal Polynomials

Orthogonal polynomials \\( \{p_n(x)\} \\) satisfy

\\[
\int_a^b p_n(x) p_m(x) w(x) \, dx = 0, \quad n \neq m.
\\]

Examples include Legendre polynomials (weight \\( w(x) = 1 \\)) on \\( [-1, 1] \\), Chebyshev polynomials, and others.

### Optimality

Gaussian quadrature with \\( n \\) points integrates exactly all polynomials of degree up to \\( 2n - 1 \\). This is the highest possible degree of exactness for any quadrature rule with \\( n \\) nodes.

### Error Properties

The error for Gaussian quadrature can be expressed as

\\[
E = \frac{f^{(2n)}(\xi)}{(2n)!} \int_a^b \left[ \prod_{i=1}^n (x - x_i) \right]^2 w(x) \, dx,
\\]

for some \\( \xi \in [a, b] \\). This indicates exponential convergence for analytic functions.

## Adaptive Quadrature Methods

Adaptive quadrature methods dynamically adjust the number and location of nodes based on the behavior of \\( f \\). By subdividing the interval and estimating local errors, these methods allocate computational effort efficiently.

Typical adaptive schemes recursively bisect intervals where the estimated error exceeds a tolerance, applying a chosen quadrature rule on subintervals until the global error criterion is met.

This approach controls truncation error effectively and is well-suited for integrands with localized features such as singularities or sharp gradients.

## Monte Carlo Integration

Monte Carlo integration approaches the problem probabilistically, estimating integrals via random sampling. For \\( I = \int_a^b f(x) \, dx \\), one generates \\( N \\) independent samples \\( x_i \\) uniformly distributed on \\( [a, b] \\) and approximates

\\[
I \approx \frac{b - a}{N} \sum_{i=1}^N f(x_i).
\\]

### Convergence Rate

The standard error decreases as

\\[
\mathrm{SE} \sim \frac{\sigma}{\sqrt{N}},
\\]

where \\( \sigma^2 \\) is the variance of \\( f(x) \\) on \\( [a, b] \\). This slow \\( O(N^{-1/2}) \\) convergence is independent of dimension, making Monte Carlo methods advantageous for high-dimensional integrals.

### Applications

Monte Carlo integration is widely used in statistical physics, Bayesian inference, financial mathematics, and other fields where high-dimensional integrals arise and deterministic methods become infeasible.

## Applications of Numerical Integration

Numerical integration is indispensable in situations where analytic integration is impossible or impractical:

- **Physics:** Computing path integrals, expectation values, and solving integral equations.

- **Engineering:** Evaluating forces, fluxes, and responses in systems modeled by integral expressions.

- **Computational Science:** Approximating integrals in finite element methods, solving partial differential equations, and performing uncertainty quantification.

In all these domains, careful consideration of the integration method, error control, and computational cost is essential for obtaining reliable and efficient results.
