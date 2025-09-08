
# Distributions

## Theoretical Foundation of Probability Distributions

A **probability distribution** is a mathematical law that governs the behavior of a random variable. It specifies how probabilities are assigned to possible outcomes in the sample space. For a random variable \\(X\\), the probability distribution encodes the likelihood of each event or value that \\(X\\) can assume.

Formally, for a random variable \\(X\\) defined on a probability space \\((\\Omega, \\mathcal{F}, P)\\), the distribution is the function that maps measurable subsets \\(A \\subseteq \\mathbb{R}\\) to probabilities:
\\[
P_X(A) = P(X \\in A)
\\]
The law of \\(X\\) is completely described by its distribution function.

Probability distributions are classified as **discrete** or **continuous** according to the nature of the random variable.

---

## Discrete Distributions

A **discrete random variable** takes values in a countable set, such as \\(\\mathbb{N}\\) or a finite subset of \\(\\mathbb{Z}\\). The probability distribution is characterized by the **probability mass function (pmf)**:
\\[
p_X(k) = P(X = k), \\qquad k \\in \\mathcal{X}
\\]
where \\(\\mathcal{X}\\) is the support of \\(X\\).

### Bernoulli Distribution
The Bernoulli distribution models a single trial with two outcomes (success with probability \\(p\\), failure with probability \\(1-p\\)):
\\[
p_X(k) =
\\begin{cases}
    p & \\text{if } k = 1 \\\\
    1-p & \\text{if } k = 0 \\\\
    0 & \\text{otherwise}
\\end{cases}
\\]

### Binomial Distribution
The binomial distribution describes the number of successes in \\(n\\) independent Bernoulli trials with success probability \\(p\\):
\\[
p_X(k) = \\binom{n}{k} p^k (1-p)^{n-k}, \\qquad k = 0, 1, \\ldots, n
\\]

### Geometric Distribution
The geometric distribution gives the probability that the first success occurs on the \\(k\\)-th trial:
\\[
p_X(k) = (1-p)^{k-1} p, \\qquad k = 1, 2, \\ldots
\\]

### Poisson Distribution
The Poisson distribution models the number of events occurring in a fixed interval, given the average rate \\(\\lambda > 0\\):
\\[
p_X(k) = \\frac{\\lambda^k}{k!} e^{-\\lambda}, \\qquad k = 0, 1, 2, \\ldots
\\]

---

## Continuous Distributions

A **continuous random variable** takes values in an uncountable set, typically \\(\\mathbb{R}\\) or a subset thereof. The distribution is described by a **probability density function (pdf)** \\(f_X(x)\\), so that for any interval \\([a, b]\\),
\\[
P(a \\leq X \\leq b) = \\int_a^b f_X(x)\\ dx
\\]
The **cumulative distribution function (cdf)** is defined as
\\[
F_X(x) = P(X \\leq x) = \\int_{-\\infty}^x f_X(t)\\ dt
\\]

### Uniform Distribution
The continuous uniform distribution on \\([a, b]\\) is defined by
\\[
f_X(x) =
\\begin{cases}
    \\frac{1}{b-a} & \\text{if } a \\leq x \\leq b \\\\
    0 & \\text{otherwise}
\\end{cases}
\\]

### Normal (Gaussian) Distribution
The normal distribution with mean \\(\\mu\\) and variance \\(\\sigma^2\\) has
\\[
f_X(x) = \\frac{1}{\\sqrt{2\\pi \\sigma^2}} \\exp\\left(-\\frac{(x-\\mu)^2}{2\\sigma^2}\\right), \\qquad x \\in \\mathbb{R}
\\]

### Exponential Distribution
The exponential distribution with rate parameter \\(\\lambda > 0\\) is
\\[
f_X(x) =
\\begin{cases}
    \\lambda e^{-\\lambda x} & x \\geq 0 \\\\
    0 & x < 0
\\end{cases}
\\]

### Gamma Distribution
The gamma distribution with shape \\(\\alpha > 0\\) and rate \\(\\beta > 0\\) is given by
\\[
f_X(x) = \\frac{\\beta^{\\alpha}}{\\Gamma(\\alpha)} x^{\\alpha-1} e^{-\\beta x}, \\qquad x \\geq 0
\\]
where \\(\\Gamma(\\alpha)\\) is the gamma function.

### Beta Distribution
The beta distribution with parameters \\(\\alpha > 0\\), \\(\\beta > 0\\) on \\([0,1]\\):
\\[
f_X(x) = \\frac{\\Gamma(\\alpha+\\beta)}{\\Gamma(\\alpha)\\Gamma(\\beta)} x^{\\alpha-1} (1-x)^{\\beta-1}, \\qquad 0 < x < 1
\\]

---

## Probability Mass, Density, and Cumulative Distribution Functions

- **pmf**: For discrete \\(X\\), \\(p_X(k) = P(X = k)\\).
- **pdf**: For continuous \\(X\\), \\(f_X(x)\\) such that \\(P(a \\leq X \\leq b) = \\int_a^b f_X(x)\\ dx\\).
- **cdf**: For any \\(X\\), \\(F_X(x) = P(X \\leq x)\\). It is non-decreasing, right-continuous, with \\(F_X(-\\infty) = 0\\), \\(F_X(+\\infty) = 1\\).

---

## Moments and Their Generating Functions

The **moments** of a distribution describe its shape and central tendency:
- The \\(n\\)-th moment: \\(\\mathbb{E}[X^n]\\)
- **Mean** (first moment): \\(\\mu = \\mathbb{E}[X]\\)
- **Variance**: \\(\\sigma^2 = \\mathbb{E}[(X - \\mu)^2]\\)
- **Skewness**: \\(\\mathbb{E}\\left[\\left(\\frac{X-\\mu}{\\sigma}\\right)^3\\right]\\)
- **Kurtosis**: \\(\\mathbb{E}\\left[\\left(\\frac{X-\\mu}{\\sigma}\\right)^4\\right]\\)

The **moment generating function (mgf)** is defined as
\\[
M_X(t) = \\mathbb{E}[e^{tX}]
\\]
when it exists in a neighborhood of \\(t=0\\). The \\(n\\)-th derivative at \\(t=0\\) gives the \\(n\\)-th moment.

The **characteristic function** is
\\[
\\varphi_X(t) = \\mathbb{E}[e^{itX}]
\\]
which always exists and uniquely determines the distribution.

---

## Relationships Between Distributions

Distributions are often related through limiting processes or parameterizations:
- The **normal approximation to the binomial**: For large \\(n\\), the binomial \\(\\operatorname{Bin}(n, p)\\) is approximated by \\(\\mathcal{N}(np, np(1-p))\\).
- The **Poisson limit of the binomial**: If \\(n \\to \\infty\\), \\(p \\to 0\\) such that \\(np = \\lambda\\) fixed, then \\(\\operatorname{Bin}(n, p) \\to \\operatorname{Poisson}(\\lambda)\\).
- The **exponential distribution** is a special case of the gamma distribution with shape parameter \\(\\alpha = 1\\).
- The **beta and gamma distributions** are related through normalization and appear as conjugate priors in Bayesian inference.

---

## Importance in Modeling and Applications

Probability distributions are fundamental to modeling random phenomena in nature, engineering, and the social sciences. They provide the theoretical underpinning for statistical inference, hypothesis testing, estimation, and prediction. The choice of distribution reflects assumptions about the underlying process and allows for the quantification of uncertainty, risk, and variability.

Distributions such as the normal, Poisson, and exponential appear ubiquitously in physical, biological, and engineering contexts due to the central limit theorem, law of rare events, and memoryless property, respectively. Understanding their properties is essential for both theoretical developments and practical applications.
