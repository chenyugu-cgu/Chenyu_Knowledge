# Integration

Integration is a core concept in calculus, serving as the mathematical counterpart to differentiation. While differentiation measures rates of change (how a quantity changes instantaneously), integration focuses on the accumulation of quantities, such as area, volume, and total change over an interval. In essence, integration allows us to sum infinitely many infinitesimal contributions to obtain a total.

## Accumulation and Area Under Curves

The most common geometric interpretation of integration is the calculation of the area under a curve. If a function \\( f(x) \\) is defined on an interval \\([a, b]\\), the definite integral of \\( f \\) from \\( a \\) to \\( b \\) represents the net area between the graph of \\( f \\) and the \\( x \\)-axis over that interval.

## Definition of the Definite Integral (Riemann Sum)

The definite integral is formally defined as the limit of a Riemann sum. We partition the interval \\([a, b]\\) into \\( n \\) subintervals of width \\( \Delta x \\), choose sample points \\( x_i^* \\) in each subinterval, and sum the areas of rectangles:

\\[
\int_a^b f(x)\\ dx = \lim_{n \to \infty} \sum_{i=1}^n f(x_i^*)\ \Delta x
\\]

If this limit exists, \\( f \\) is said to be Riemann integrable on \\([a, b]\\).

## Indefinite Integrals and Antiderivatives

An indefinite integral represents a family of all antiderivatives of a function. If \\( F(x) \\) is an antiderivative of \\( f(x) \\), then:

\\[
\int f(x)\ dx = F(x) + C
\\]

where \\( C \\) is an arbitrary constant of integration.

## The Fundamental Theorem of Calculus

The Fundamental Theorem of Calculus (FTC) connects differentiation and integration:

1. **First Part:** If \\( f \\) is continuous on \\([a, b]\\), and \\( F(x) = \int_a^x f(t)\ dt \\), then \\( F'(x) = f(x) \\). That is, integration followed by differentiation returns the original function.
2. **Second Part:** If \\( F \\) is any antiderivative of \\( f \\) on \\([a, b]\\), then:

\\[
\int_a^b f(x)\ dx = F(b) - F(a)
\\]

## Basic Integration Rules

### Power Rule
For \\( n \neq -1 \\):
\\[
\int x^n\ dx = \frac{x^{n+1}}{n+1} + C
\\]

### Substitution (Change of Variables)
If \\( u = g(x) \\) and \\( f \\) is continuous:
\\[
\int f(g(x))\ g'(x)\ dx = \int f(u)\ du
\\]

### Integration by Parts
Based on the product rule for differentiation:
\\[
\int u\ dv = u v - \int v\ du
\\]
where \\( u = u(x) \\), \\( v = v(x) \\).

## Improper Integrals and Convergence

Improper integrals extend the concept of integration to unbounded intervals or unbounded functions. For example:
\\[
\int_a^{\infty} f(x)\ dx = \lim_{b \to \infty} \int_a^b f(x)\ dx
\\]

Or, if \\( f(x) \\) has a singularity at \\( c \\) in \\([a, b]\\):
\\[
\int_a^b f(x)\ dx = \lim_{\epsilon \to 0^+} \int_a^{c-\epsilon} f(x)\ dx + \int_{c+\epsilon}^b f(x)\ dx
\\]

An improper integral converges if the corresponding limit exists and is finite.

## Applications in Science and Engineering

Integration is used to solve a wide variety of problems:

- **Areas:** Compute the area under curves or between curves.
- **Volumes:** Find the volume of solids of revolution and other shapes.
- **Work:** Calculate work done by a variable force.
- **Probability:** Find probabilities and expected values using probability density functions.
- **Other accumulations:** Total mass, charge, energy, etc., given a density function.

## Cookbook Overview: Structure of Integration Recipes

Each integration recipe in this cookbook will be organized as follows:

- **Purpose:** What the integration technique or formula is used for.
- **Background:** Mathematical context or intuition.
- **Ingredients:** Functions, substitutions, and preconditions required.
- **Method:** Step-by-step procedure for applying the technique.
- **Example:** A worked-out sample problem.
- **Result:** The general form or outcome of the method.
- **Variations:** Related techniques, special cases, or extensions.
- **References:** Sources for further reading or deeper understanding.