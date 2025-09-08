# Probability and Statistics

Probability theory provides a rigorous mathematical framework to model uncertainty and random phenomena. Statistics applies probabilistic concepts to infer properties about populations from data. This section introduces the foundational theoretical concepts in probability and statistics.

## Axiomatic Definition of Probability (Kolmogorov Axioms)

Probability is defined on a mathematical structure called a probability space \\((\Omega, \mathcal{F}, P)\\), where:

- \\(\Omega\\) is the *sample space*, the set of all possible outcomes.
- \\(\mathcal{F}\\) is a *sigma-algebra* (or \\(\sigma\\)-algebra) of subsets of \\(\Omega\\), called *events*.
- \\(P: \mathcal{F} \to [0, 1]\\) is a *probability measure* satisfying the Kolmogorov axioms:

1. **Non-negativity:** For any event \\(A \in \mathcal{F}\\), \\(P(A) \geq 0\\).
2. **Normalization:** \\(P(\Omega) = 1\\).
3. **Countable Additivity (\\(\sigma\\)-additivity):** For any countable sequence of pairwise disjoint events \\(\{A_i\}_{i=1}^\infty \subset \mathcal{F}\\),
   \\[
   P\left(\bigcup_{i=1}^\infty A_i\right) = \sum_{i=1}^\infty P(A_i)
   \\]

## Sample Spaces, Events, and Sigma-Algebras

- The *sample space* \\(\Omega\\) represents all possible outcomes of a random experiment.
- An *event* is any element of \\(\mathcal{F}\\), i.e., a subset of \\(\Omega\\).
- The *sigma-algebra* \\(\mathcal{F}\\) is a collection of subsets of \\(\Omega\\) that includes \\(\Omega\\) itself, is closed under complementation, and closed under countable unions.

## Conditional Probability and Bayes' Theorem

The *conditional probability* of an event \\(A\\) given \\(B\\) (with \\(P(B) > 0\\)) is defined as
\\[
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
\\]

*Bayes' theorem* relates conditional probabilities:
\\[
P(A \mid B) = \frac{P(B \mid A) P(A)}{P(B)}
\\]

## Random Variables, Probability Mass and Density Functions

A *random variable* is a measurable function \\(X: \Omega \to \mathbb{R}\\) (or more generally, to some measurable space).

- *Discrete random variables* take countable values. Their distribution is described by a *probability mass function* (pmf) \\(p_X(x) = P(X = x)\\).
- *Continuous random variables* take values in an interval (or more general uncountable set). Their distribution is described by a *probability density function* (pdf) \\(f_X(x)\\), where
  \\[
  P(a \leq X \leq b) = \int_a^b f_X(x) \ dx
  \\]
  and \\(\int_{-\infty}^{\infty} f_X(x) \ dx = 1\\).

## Expectation, Variance, Covariance, and Moments

- The *expectation* (mean) of a random variable \\(X\\) is
  - Discrete: \\(\mathbb{E}[X] = \sum_x x \ p_X(x)\\)
  - Continuous: \\(\mathbb{E}[X] = \int_{-\infty}^{\infty} x \ f_X(x) \ dx\\)
- The *variance* is \\(\mathrm{Var}(X) = \mathbb{E}[(X - \mathbb{E}[X])^2]\\).
- The *covariance* of random variables \\(X\\) and \\(Y\\) is \\(\mathrm{Cov}(X, Y) = \mathbb{E}[(X - \mathbb{E}[X])(Y - \mathbb{E}[Y])]\\).
- The \\(n\\)-th *moment* of \\(X\\) is \\(\mathbb{E}[X^n]\\); the *central moment* is \\(\mathbb{E}[(X - \mathbb{E}[X])^n]\\).

## Common Probability Distributions

- **Binomial distribution:** Models the number of successes in \\(n\\) independent Bernoulli trials with probability \\(p\\) of success.
  \\[
  P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}
  \\]
- **Poisson distribution:** Models the number of events in a fixed interval of time or space with rate \\(\lambda\\).
  \\[
  P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!}
  \\]
- **Normal (Gaussian) distribution:** Continuous distribution with mean \\(\mu\\) and variance \\(\sigma^2\\).
  \\[
  f(x) = \frac{1}{\sqrt{2\pi \sigma^2}} \exp\left( -\frac{(x - \mu)^2}{2\sigma^2} \right)
  \\]
- **Exponential distribution:** Models waiting times between Poisson events.
  \\[
  f(x) = \lambda e^{-\lambda x}, \quad x \geq 0
  \\]
- Other important distributions include the uniform, geometric, beta, gamma, and chi-squared distributions.

## Law of Large Numbers and Central Limit Theorem

- **Law of Large Numbers (LLN):** The sample mean of independent, identically distributed (i.i.d.) random variables converges (in probability) to the expected value as the sample size increases.
  \\[
  \frac{1}{n} \sum\_{i=1}^n X_i \xrightarrow{P} \mathbb{E}[X]
  \\]
- **Central Limit Theorem (CLT):** The properly normalized sum of i.i.d. random variables with finite mean and variance converges in distribution to a normal distribution as \\(n\\) increases.
  \\[
  \frac{\sum\_{i=1}^n X_i - n\mu}{\sigma\sqrt{n}} \xrightarrow{d} \mathcal{N}(0, 1)
  \\]

## Introduction to Statistics

*Statistics* is concerned with collecting, analyzing, interpreting, and presenting data.

- A *population* is the entire set of items or individuals of interest.
- A *sample* is a subset drawn from the population.
- *Estimation* involves inferring population parameters (such as mean or variance) from sample statistics.
- *Hypothesis testing* is the process of using sample data to assess the plausibility of a hypothesis about a population parameter, often via test statistics and p-values.

## Role of Probability and Statistics

Probability and statistics are foundational in engineering, science, and data analysis. They provide the theoretical basis for modeling uncertainty, designing experiments, making predictions, and drawing inferences from data. Applications range from reliability analysis in engineering, statistical inference in scientific research, to probabilistic modeling and machine learning in data science.