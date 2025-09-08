
# Law of Large Numbers & CLT

## Law of Large Numbers (LLN)

The Law of Large Numbers is a fundamental theorem in probability theory describing the behavior of the average of a sequence of independent, identically distributed (i.i.d.) random variables as the number of variables increases. It formalizes the intuition that as more observations are collected, the sample mean will tend to get closer to the expected value.

Let \\( X\_1, X\_2, \ldots \\) be a sequence of i.i.d. random variables with finite expected value \\( \\mathbb{E}[X\_1] = \\mu \\).

### Weak Law of Large Numbers (WLLN)

The Weak Law of Large Numbers states that, for any \\( \\varepsilon > 0 \\),
\\[
    \lim\\_{n \\to \\infty} \\mathbb{P} \\left( \\left| \\frac{1}{n} \sum\_{i=1}^n X\_i - \\mu \\right| > \\varepsilon \\right) = 0.
\\]
This means that the sample mean \\( S\_n = \\frac{1}{n} \sum\_{i=1}^n X\_i \\) converges in probability to \\( \\mu \\):
\\[
    S\\_n \\xrightarrow{P} \\mu.
\\]

### Strong Law of Large Numbers (SLLN)

The Strong Law of Large Numbers strengthens this result by asserting almost sure convergence:
\\[
    \mathbb{P} \\left( \lim\_{n \\to \\infty} S\_n = \\mu \\right) = 1,
\\]
or equivalently,
\\[
    S\_n \\xrightarrow{a.s.} \\mu.
\\]
Here, \\( \\xrightarrow{a.s.} \\) denotes almost sure convergence.

#### Formal Definitions of Convergence
- **Convergence in probability**: A sequence of random variables \\( Y\_n \\) converges in probability to \\( Y \\) if for all \\( \\varepsilon > 0 \\),
  \\[
      \lim\_{n \\to \\infty} \\mathbb{P} \\left( |Y\_n - Y| > \\varepsilon \\right) = 0.
  \\]
- **Almost sure convergence**: \\( Y\_n \\) converges almost surely to \\( Y \\) if
  \\[
      \mathbb{P} \\left( \lim\_{n \\to \\infty} Y\\_n = Y \\right) = 1.
  \\]

#### Intuition
The LLN ensures that the sample mean \\( S\_n \\) becomes arbitrarily close to the expected value \\( \\mu \\) as \\( n \\) increases, either with high probability (WLLN) or almost surely (SLLN). This underpins the reliability of empirical averages as estimators of the true mean.

## Central Limit Theorem (CLT)

The Central Limit Theorem is another cornerstone of probability theory. It describes the limiting distribution of the normalized sum of i.i.d. random variables.

Let \\( X\_1, X\_2, \ldots \\) be i.i.d. random variables with finite mean \\( \\mu = \\mathbb{E}[X\_1] \\) and finite, positive variance \\( \\sigma^2 = \\mathrm{Var}(X\_1) \\).

Define the standardized sum:
\\[
    Z\\_n = \\frac{1}{\sigma \sqrt{n}} \sum\_{i=1}^n (X\\_i - \\mu) = \sqrt{n} \frac{S\\_n - \\mu}{\sigma}
\\]

Then, the CLT states that as \\( n \\to \\infty \\),
\\[
    Z\\_n \\xrightarrow{d} N(0, 1),
\\]
where \\( \\xrightarrow{d} \\) denotes convergence in distribution and \\( N(0, 1) \\) is the standard normal distribution.

### Importance of Finite Mean and Variance
The assumptions of finite mean and variance are crucial. If the variance is infinite or undefined, the limiting distribution may not be normal, and other limit theorems (such as those for stable laws) may apply.

### Lindeberg–Feller Central Limit Theorem
The classical CLT requires i.i.d. variables, but more general forms exist. The Lindeberg–Feller CLT applies to sequences of independent (not necessarily identically distributed) random variables \\( \\{X\_i\\} \\) with means \\( \\mu\_i \\) and variances \\( \\sigma\_i^2 \\), provided the total variance \\( s\_n^2 = \sum\_{i=1}^n \\sigma\\_i^2 \\) grows without bound and the Lindeberg condition is satisfied:
\\[
    \forall \\varepsilon > 0, \quad \lim\_{n \\to \\infty} \frac{1}{s\\_n^2} \sum\_{i=1}^n \mathbb{E} \\left[ (X\\_i - \\mu\\_i)^2 \\ \\mathbb{I}\_{\\{|X\\_i - \\mu\\_i| > \varepsilon s\\_n\\}} \\right] = 0.
\\]
Under these conditions,
\\[
    \frac{1}{s\\_n} \sum\_{i=1}^n (X\\_i - \\mu\\_i) \\xrightarrow{d} N(0, 1).
\\]

## Theoretical Importance

The Law of Large Numbers and the Central Limit Theorem are foundational results in probability and statistics:
- The LLN provides the theoretical justification for using sample averages to estimate expected values, ensuring that empirical means are reliable estimators as the sample size increases.
- The CLT explains why, under broad conditions, the distribution of normalized sums (or averages) of random variables approaches the normal distribution, regardless of the original distribution. This underlies the widespread appearance of the normal distribution in statistical inference.
- Both the LLN and CLT justify statistical procedures such as estimation and hypothesis testing, forming the backbone of frequentist inference.
