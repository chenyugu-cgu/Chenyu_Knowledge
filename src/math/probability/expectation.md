
# Expectation and Variance

## Expectation

The **expectation** (or expected value, mean) of a random variable provides a fundamental measure of its central tendency. For a discrete random variable \\(X\\) with probability mass function \\(p(x)\\), the expectation is defined as
\\[
E[X] = \\sum\\_{x} x\\ p(x)
\\]
where the sum is over all possible values \\(x\\) that \\(X\\) can take.

For a continuous random variable \\(X\\) with probability density function \\(f(x)\\), the expectation is defined as
\\[
E[X] = \\int\\_{-\\infty}^{\\infty} x\\ f(x)\\ dx
\\]
provided the integral converges absolutely.

Expectation can be interpreted as the long-run average value of the random variable after many independent realizations.

### Linearity of Expectation

Expectation is a linear operator: for any random variables \\(X\\), \\(Y\\) and real numbers \\(a\\), \\(b\\),
\\[
E[a X + b Y] = a E[X] + b E[Y]
\\]
This property holds regardless of whether \\(X\\) and \\(Y\\) are independent.

More generally, for any finite collection \\(\\{X\\_i\\}\\) and real coefficients \\(\\{a\\_i\\}\\),
\\[
E\\left[\sum\_{i=1}^n a\\_i X\\_i\\right] = \sum\_{i=1}^n a\\_i E[X\\_i]
\\]

Linearity of expectation allows for the computation of expected values of sums of random variables without requiring knowledge of their dependence structure.

## Variance

The **variance** of a random variable \\(X\\) quantifies the dispersion of \\(X\\) around its expectation:
\\[
\\operatorname{Var}(X) = E\\left[(X - E[X])^2\\right]
\\]
Variance measures the average squared deviation from the mean.

An equivalent and often useful formula is
\\[
\\operatorname{Var}(X) = E[X^2] - (E[X])^2
\\]
This follows from expanding the definition:
\\[
E\\left[(X - E[X])^2\\right] = E[X^2 - 2 X E[X] + (E[X])^2] = E[X^2] - 2 E[X] E[X] + (E[X])^2 = E[X^2] - (E[X])^2
\\]

Variance is always non-negative, and equals zero if and only if \\(X\\) is almost surely constant.

## Covariance and Correlation

The **covariance** between two random variables \\(X\\) and \\(Y\\) is defined as
\\[
\\operatorname{Cov}(X, Y) = E\\left[(X - E[X])(Y - E[Y])\\right] = E[XY] - E[X] E[Y]
\\]
Covariance measures the joint variability of \\(X\\) and \\(Y\\). If \\(\\operatorname{Cov}(X, Y) = 0\\), \\(X\\) and \\(Y\\) are said to be uncorrelated.

The **correlation coefficient** (Pearson correlation) is a normalized measure of linear dependence:
\\[
\\rho(X, Y) = \\frac{\\operatorname{Cov}(X, Y)}{\\sqrt{\\operatorname{Var}(X)} \\ \\sqrt{\\operatorname{Var}(Y)}}
\\]
with \\(-1 \\leq \\rho(X, Y) \\leq 1\\).

## Properties under Transformations

Let \\(a, b \\in \\mathbb{R}\\) and \\(X\\) a random variable.

- **Expectation under affine transformation**:
  \\[
  E[a X + b] = a E[X] + b
  \\]
- **Variance under affine transformation**:
  \\[
  \\operatorname{Var}(a X + b) = a^2 \\operatorname{Var}(X)
  \\]
  The additive constant \\(b\\) does not affect variance; scaling by \\(a\\) multiplies the variance by \\(a^2\\).

If \\(X\\) and \\(Y\\) are independent, then
\\[
\\operatorname{Var}(X + Y) = \\operatorname{Var}(X) + \\operatorname{Var}(Y)
\\]
In general,
\\[
\\operatorname{Var}(X + Y) = \\operatorname{Var}(X) + \\operatorname{Var}(Y) + 2 \\operatorname{Cov}(X, Y)
\\]

## Higher-Order Moments and Central Moments

The \\(k\\)-th **moment** of \\(X\\) is \\(E[X^k]\\). The \\(k\\)-th **central moment** is \\(E[(X - E[X])^k]\\). The first central moment is zero; the second central moment is the variance.

Higher-order moments describe additional aspects of the distribution:
- The third central moment (skewness) measures asymmetry.
- The fourth central moment (kurtosis) measures tail heaviness.

## Importance and Applications

Expectation and variance are foundational in probability theory and statistics. Expectation provides a measure of the "center" of a distribution, while variance quantifies the spread. These concepts are essential in:
- Law of Large Numbers and Central Limit Theorem.
- Statistical estimation and hypothesis testing.
- Error analysis and uncertainty quantification.
- Risk assessment in finance and engineering.

They also play a crucial role in defining other statistical measures, constructing estimators, and analyzing the behavior of random processes.
