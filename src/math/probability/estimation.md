
# Statistical Estimation

Statistical estimation is a foundational concept in probability and statistics, concerned with inferring the values of unknown parameters of a population or probability distribution based on observed data. The theory of estimation provides rigorous frameworks for constructing estimators, analyzing their properties, and quantifying the uncertainty inherent in the estimation process.

## Point Estimation and Interval Estimation

**Point estimation** refers to the process of providing a single "best guess" value for an unknown parameter \\(\\theta\\) based on sample data. Formally, a point estimator is a function \\(\\hat{\\theta}(X)\\) of the observed data \\(X\\), intended to estimate \\(\\theta\\).

**Interval estimation** extends this idea by providing a range of plausible values for the parameter, usually with a specified probability of containing the true value. Such an interval is called a confidence interval in the frequentist framework or a credible interval in the Bayesian framework.

## Properties of Estimators

Theoretical evaluation of estimators involves several key properties:

- **Unbiasedness:** An estimator \\(\\hat{\\theta}\\) is unbiased for \\(\\theta\\) if \\(\\mathbb{E}[\\hat{\\theta}] = \\theta\\) for all \\(\\theta\\) in the parameter space. That is, the estimator's expected value equals the true parameter value.

- **Consistency:** An estimator \\(\\hat{\\theta}\\_n\\) (based on a sample of size \\(n\\)) is consistent if \\(\\hat{\\theta}\\_n \\to \\theta\\) in probability as \\(n \\to \\infty\\). Formally, for every \\(\\epsilon > 0\\),
  \\[
    \\lim\\_{n \\to \\infty} \\mathbb{P}(|\\hat{\\theta}\\_n - \\theta| > \\epsilon) = 0.
  \\]

- **Efficiency:** Among all unbiased estimators, an efficient estimator has the smallest possible variance. The variance of an efficient estimator achieves the lower bound given by the Cramér–Rao inequality, whenever such a bound exists.

- **Sufficiency:** An estimator (or statistic) \\(T(X)\\) is sufficient for \\(\\theta\\) if the conditional distribution of the data \\(X\\) given \\(T(X)\\) does not depend on \\(\\theta\\). Sufficiency formalizes the idea that \\(T(X)\\) captures all information about \\(\\theta\\) contained in the data.

## Methods of Estimation

Several general approaches are used to construct estimators:

- **Method of Moments:** Parameters are estimated by equating sample moments to theoretical moments. If \\(m\\) parameters are to be estimated, the first \\(m\\) sample moments are set equal to the corresponding population moments, and the resulting system is solved for the parameters.

- **Maximum Likelihood Estimation (MLE):** The maximum likelihood estimator \\(\\hat{\\theta}\_{MLE}\\) is defined as
  \\[
    \hat{\theta}\_{MLE} = \underset{\theta \in \Theta}{\operatorname{argmax}} \\ L(\theta; X),
  \\]
  where \\(L(\\theta; X)\\) is the likelihood function, expressing the probability (or probability density) of the observed data as a function of \\(\\theta\\). MLEs have desirable asymptotic properties under regularity conditions.

- **Bayesian Estimation:** In the Bayesian paradigm, parameters are treated as random variables with a prior distribution \\(\\pi(\\theta)\\). The posterior distribution is given by Bayes' theorem:
  \\[
    \\pi(\\theta \\mid X) = \\frac{L(\\theta; X) \\pi(\\theta)}{\\int\_{\\Theta} L(\\theta'; X) \\pi(\\theta') d\\theta'}.
  \\]
  Bayes estimators are derived from the posterior, often as the mean, median, or mode of \\(\\pi(\\theta \\mid X)\\).

## Cramér–Rao Lower Bound and Efficiency

The **Cramér–Rao lower bound (CRLB)** provides a theoretical lower bound on the variance of any unbiased estimator \\(\\hat{\\theta}\\) of a parameter \\(\\theta\\):
\\[
  \\operatorname{Var}(\\hat{\\theta}) \\geq \\frac{1}{I(\\theta)},
\\]
where \\(I(\\theta)\\) is the Fisher information:
\\[
  I(\\theta) = \\mathbb{E}\\left[\\left(\\frac{\\partial}{\\partial\\theta} \\log f(X; \\theta)\\right)^2\\right],
\\]
with \\(f(X; \\theta)\\) denoting the probability density (or mass) function. An estimator achieving the CRLB is said to be **efficient**.

## Confidence Intervals: Theoretical Foundation

A **confidence interval** for a parameter \\(\\theta\\) is a random interval \\([L(X), U(X)]\\) constructed from the data, such that
\\[
  \\mathbb{P}(L(X) \\leq \\theta \\leq U(X)) = 1 - \\alpha,
\\]
where \\(1 - \\alpha\\) is the confidence level (e.g., 0.95). The probability statement refers to the random interval before observing the data, not to the fixed parameter after data collection. The construction of confidence intervals is often based on pivotal quantities or the asymptotic distribution of estimators.

## Asymptotic Properties of Estimators

As the sample size \\(n\\) increases, many estimators exhibit desirable asymptotic properties:

- **Asymptotic Unbiasedness:** The bias of the estimator vanishes as \\(n \\to \\infty\\).
- **Asymptotic Normality:** Under regularity conditions, suitably normalized estimators converge in distribution to a normal distribution:
  \\[
    \\sqrt{n}(\\hat{\\theta}\\_n - \\theta) \\xrightarrow{d} N(0, V(\\theta)),
  \\]
  where \\(V(\\theta)\\) is the asymptotic variance.
- **Asymptotic Efficiency:** An estimator is asymptotically efficient if its asymptotic variance attains the Cramér–Rao lower bound as \\(n \\to \\infty\\).

## Importance of Estimation in Statistical Inference and Applications

Statistical estimation is central to statistical inference, providing the means to draw conclusions about unknown population characteristics based on finite data. Accurate and theoretically justified estimation methods are essential in scientific research, engineering, economics, and many other fields where decision-making relies on quantifying uncertainty and extracting information from data.
