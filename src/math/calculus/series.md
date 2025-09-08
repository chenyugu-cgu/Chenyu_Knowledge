# Series and Sequences

Sequences and series are fundamental objects in calculus and mathematical analysis, providing the foundation for understanding limits, convergence, and the representation of functions.

## Sequences

A **sequence** is an ordered list of numbers, typically denoted as \\((a_n)\\), where \\(n\\) is a positive integer (\\(n = 1, 2, 3, \ldots\\)). Formally, a sequence is a function from the natural numbers to the real (or complex) numbers:
\\[
a_1, a_2, a_3, \ldots, a_n, \ldots
\\]
or
\\[
(a_n)_{n=1}^{\infty}
\\]

### Convergence of Sequences and Limits

A sequence \\((a_n)\\) is said to **converge** to a limit \\(L\\) if, for every \\(\varepsilon > 0\\), there exists an integer \\(N\\) such that for all \\(n > N\\), \\(|a_n - L| < \varepsilon\\). Symbolically:
\\[
\lim_{n \to \infty} a_n = L
\\]
If no such \\(L\\) exists, the sequence is **divergent**.

## Infinite Series

An **infinite series** is the sum of the terms of a sequence:
\\[
\sum_{n=1}^{\infty} a_n = a_1 + a_2 + a_3 + \cdots
\\]
The **partial sum** \\(S_N\\) is defined as:
\\[
S_N = \sum_{n=1}^{N} a_n
\\]
The series **converges** if the sequence of partial sums \\((S_N)\\) converges to a finite limit \\(S\\):
\\[
\lim_{N \to \infty} S_N = S
\\]
Otherwise, the series **diverges**.

## Convergence Tests

Determining whether a series converges is a central question. Some common tests include:

- **Geometric Series**: For \\(|r| < 1\\),
  \\[
  \sum_{n=0}^{\infty} ar^n = \frac{a}{1 - r}
  \\]
  converges; otherwise, it diverges.

- **p-Series**: The series
  \\[
  \sum_{n=1}^{\infty} \frac{1}{n^p}
  \\]
  converges if \\(p > 1\\) and diverges if \\(p \leq 1\\).

- **Comparison Test**: If \\(0 \leq a_n \leq b_n\\) for all \\(n\\) beyond some index, and \\(\sum b_n\\) converges, then \\(\sum a_n\\) converges.

- **Ratio Test**: For series with positive terms, compute
  \\[
  L = \lim_{n \to \infty} \left| \frac{a_{n+1}}{a_n} \right|
  \\]
  - If \\(L < 1\\), the series converges.
  - If \\(L > 1\\), the series diverges.
  - If \\(L = 1\\), the test is inconclusive.

- **Root Test**: Compute
  \\[
  L = \limsup_{n \to \infty} \sqrt[n]{|a_n|}
  \\]
  - If \\(L < 1\\), the series converges.
  - If \\(L > 1\\), the series diverges.
  - If \\(L = 1\\), the test is inconclusive.

## Power Series and Taylor Series

A **power series** is a series of the form
\\[
\sum_{n=0}^{\infty} a_n (x - c)^n
\\]
where \\(c\\) is the center and \\(a_n\\) are coefficients. Power series converge within a certain **radius of convergence**.

A **Taylor series** is a power series used to represent a function \\(f(x)\\) as an infinite sum of its derivatives at a point \\(a\\):
\\[
f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!} (x - a)^n
\\]
When \\(a = 0\\), it is called a **Maclaurin series**.

## Applications in Science and Engineering

Sequences and series are essential tools in many areas:
- **Approximations**: Functions are approximated by polynomials or truncated series (e.g., Taylor polynomials).
- **Signal Expansions**: Fourier series represent signals as sums of sines and cosines.
- **Numerical Methods**: Series are used to compute values of transcendental functions (e.g., exponential, logarithm, trigonometric functions).
- **Solving Differential Equations**: Series solutions provide analytic expressions for solutions.

## Cookbook Overview

Recipes in this section will be structured as follows:
- **Purpose**: What problem or calculation the recipe addresses.
- **Background**: Mathematical context and key concepts.
- **Ingredients**: Required definitions, theorems, or tools.
- **Method**: Step-by-step procedure for solving the problem or applying the technique.
- **Example**: A worked example illustrating the method.
- **Result**: Interpretation or significance of the outcome.
- **Variations**: Extensions, related problems, or alternative approaches.
- **References**: Further reading or sources for deeper study.