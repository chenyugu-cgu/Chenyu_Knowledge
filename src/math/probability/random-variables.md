# Random Variables

In probability theory, a **random variable** is a measurable function that maps outcomes of a random experiment to real numbers. Formally, given a probability space \\((\Omega, \mathcal{F}, P)\\), where \\(\Omega\\) is the sample space, \\(\mathcal{F}\\) is a sigma-algebra of events, and \\(P\\) is a probability measure, a random variable \\(X\\) is a function

\\[
X: \Omega \to \mathbb{R}
\\]

such that for every Borel set \\(B \subseteq \mathbb{R}\\), the preimage \\(X^{-1}(B) = \{ \omega \in \Omega : X(\omega) \in B \} \in \mathcal{F}\\). This measurability condition ensures that the probability \\(P(X \in B)\\) is well-defined.

Random variables serve as the fundamental objects linking abstract probability theory to practical applications in statistics, physics, engineering, and other fields. They allow the quantification of uncertainty by assigning numerical values to outcomes and facilitate the study of distributions, expectations, and other statistical properties.

## Discrete and Continuous Random Variables

Random variables are often categorized based on the nature of their range:

- **Discrete random variables** take values in at most countable sets, typically integers or finite sets.
- **Continuous random variables** take values in uncountable sets, often intervals of real numbers.

### Discrete Random Variables

For a discrete random variable \\(X\\), its distribution is characterized by the **probability mass function (pmf)**, defined as

\\[
p(x) = P(X = x)
\\]

for each possible value \\(x\\) in the range of \\(X\\). The pmf satisfies

\\[
p(x) \geq 0 \quad \text{for all } x, \quad \text{and} \quad \sum_{x} p(x) = 1.
\\]

The pmf completely determines the distribution of \\(X\\).

### Continuous Random Variables

For a continuous random variable \\(X\\), its distribution is described by a **probability density function (pdf)** \\(f(x)\\), which is a non-negative function satisfying

\\[
\int_{-\infty}^{\infty} f(x) \, dx = 1.
\\]

The probability that \\(X\\) lies within an interval \\([a, b]\\) is given by

\\[
P(a \leq X \leq b) = \int_{a}^{b} f(x) \, dx.
\\]

The pdf itself is not a probability but rather a density; probabilities correspond to integrals of the pdf over sets.

## Cumulative Distribution Function

The **cumulative distribution function (cdf)** of a random variable \\(X\\) is defined as

\\[
F(x) = P(X \leq x).
\\]

The cdf has the following properties:

1. **Non-decreasing:** \\(F(x_1) \leq F(x_2)\\) whenever \\(x_1 < x_2\\).
2. **Right-continuous:** \\(\lim_{h \to 0^+} F(x + h) = F(x)\\).
3. **Limits:** \\(\lim_{x \to -\infty} F(x) = 0\\) and \\(\lim_{x \to \infty} F(x) = 1\\).

The cdf uniquely determines the distribution of \\(X\\), whether discrete, continuous, or mixed.

## Expectation, Variance, and Moments

The **expectation** or **mean** of a random variable \\(X\\), denoted \\(E[X]\\), is a measure of its central tendency. It is defined as

- For discrete \\(X\\):

\\[
E[X] = \sum_{x} x \, p(x),
\\]

provided the sum converges absolutely.

- For continuous \\(X\\):

\\[
E[X] = \int_{-\infty}^{\infty} x \, f(x) \, dx,
\\]

provided the integral is finite.

The **variance** of \\(X\\), denoted \\(\operatorname{Var}(X)\\), measures the dispersion of \\(X\\) around its mean:

\\[
\operatorname{Var}(X) = E[(X - E[X])^2] = E[X^2] - (E[X])^2,
\\]

where the second moment \\(E[X^2]\\) is defined analogously.

Higher-order moments \\(E[X^n]\\) for \\(n \in \mathbb{N}\\) provide further information about the shape of the distribution, including skewness and kurtosis.

## Joint Distributions

When considering multiple random variables \\(X_1, X_2, \ldots, X_n\\), their joint behavior is described by a **joint distribution**. For example, the joint cdf is

\\[
F_{X_1, \ldots, X_n}(x_1, \ldots, x_n) = P(X_1 \leq x_1, \ldots, X_n \leq x_n).
\\]

If the random variables are discrete, the joint pmf is

\\[
p(x_1, \ldots, x_n) = P(X_1 = x_1, \ldots, X_n = x_n).
\\]

If continuous, the joint pdf \\(f(x_1, \ldots, x_n)\\) satisfies

\\[
P\big( (X_1, \ldots, X_n) \in A \big) = \int_{A} f(x_1, \ldots, x_n) \, dx_1 \cdots dx_n
\\]

for measurable sets \\(A \subseteq \mathbb{R}^n\\).

### Marginal and Conditional Distributions

The **marginal distribution** of a subset of random variables is obtained by integrating or summing out the other variables. For instance, the marginal pdf of \\(X_1\\) is

\\[
f_{X_1}(x_1) = \int_{\mathbb{R}^{n-1}} f(x_1, x_2, \ldots, x_n) \, dx_2 \cdots dx_n.
\\]

The **conditional distribution** of \\(X_1\\) given \\(X_2 = x_2\\) is defined via

\\[
f_{X_1 | X_2}(x_1 | x_2) = \frac{f_{X_1, X_2}(x_1, x_2)}{f_{X_2}(x_2)},
\\]

provided \\(f_{X_2}(x_2) > 0\\).

## Independence

Two random variables \\(X\\) and \\(Y\\) are **independent** if for all measurable sets \\(A, B \subseteq \mathbb{R}\\),

\\[
P(X \in A, Y \in B) = P(X \in A) \, P(Y \in B).
\\]

Equivalently, their joint distribution factorizes as the product of marginals:

- For discrete variables:

\\[
p_{X,Y}(x,y) = p_X(x) \, p_Y(y).
\\]

- For continuous variables:

\\[
f_{X,Y}(x,y) = f_X(x) \, f_Y(y).
\\]

Independence implies that knowing the value of one variable provides no information about the other.

---

Random variables provide the essential framework for modeling uncertainty and variability in many domains. By formalizing the notion of measurable functions on probability spaces, they enable a rigorous mathematical treatment of stochastic phenomena, bridging theoretical probability and practical applications.
