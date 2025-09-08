# Hypothesis Testing

Hypothesis testing is a fundamental framework in statistics used to make inferences about populations based on sample data. Its primary purpose is to evaluate whether there is enough evidence in a sample to support a specific claim or hypothesis about a population parameter.

## Definition and Purpose

Formally, hypothesis testing involves formulating two mutually exclusive hypotheses:

- The **null hypothesis** \\(H_0\\), which represents the default or status quo assumption.
- The **alternative hypothesis** \\(H_1\\), which represents the claim or effect we want to test for.

The goal is to use observed data to decide whether to reject \\(H_0\\) in favor of \\(H_1\\), or fail to reject \\(H_0\\), based on the evidence.

## Hypotheses

The null hypothesis \\(H_0\\) is a statement about the population parameter that is assumed true until evidence suggests otherwise. For example, \\(H_0: \mu = \mu_0\\) states that the population mean equals some value \\(\mu_0\\).

The alternative hypothesis \\(H_1\\) is the complement, representing a different value or range of values for the parameter, such as \\(H_1: \mu \neq \mu_0\\), \\(H_1: \mu > \mu_0\\), or \\(H_1: \mu < \mu_0\\).

## Test Statistics and Their Distributions

A **test statistic** is a function of the observed data used to summarize the evidence against \\(H_0\\). Its distribution under the assumption that \\(H_0\\) is true is known or can be approximated. This distribution forms the basis for decision-making.

Let \\(T(X)\\) denote the test statistic computed from sample data \\(X\\). Under \\(H_0\\), \\(T(X)\\) follows a probability distribution \\(F_{T|H_0}\\). The observed value \\(t_{obs}\\) is compared against this distribution to assess the plausibility of \\(H_0\\).

## p-values and Significance Levels

The **p-value** is the probability, under \\(H_0\\), of observing a test statistic as extreme or more extreme than \\(t_{obs}\\). Formally,

\\[
p = P_{H_0}(T(X) \geq t_{obs}) \quad \text{(for right-tailed tests)}
\\]

or analogously for left-tailed and two-tailed tests.

A **significance level** \\(\alpha\\) is a pre-specified threshold that controls the probability of incorrectly rejecting \\(H_0\\) when it is true. If \\(p \leq \alpha\\), we reject \\(H_0\\); otherwise, we fail to reject it.

## Types of Errors and Power

Two types of errors can occur in hypothesis testing:

- **Type I error**: Rejecting \\(H_0\\) when it is true. The probability of this error is the significance level \\(\alpha\\).
- **Type II error**: Failing to reject \\(H_0\\) when \\(H_1\\) is true. The probability of this error is denoted \\(\beta\\).

The **power** of a test is the probability of correctly rejecting \\(H_0\\) when \\(H_1\\) is true, given by

\\[
\text{Power} = 1 - \beta = P_{H_1}(\text{reject } H_0)
\\]

Power depends on the true parameter value under \\(H_1\\), the sample size, the significance level, and the test statistic.

## Common Hypothesis Tests

Several classical tests arise from this framework:

- **z-test**: Tests hypotheses about population means when the variance is known and the sample size is large, using the standard normal distribution.
- **t-test**: Used when the population variance is unknown and estimated from the sample, relying on Student's t-distribution.
- **chi-square test**: Common in testing hypotheses about categorical data or variances.
- **F-test**: Used to compare variances or test hypotheses about multiple means in analysis of variance (ANOVA).

Each test uses a specific test statistic with a known null distribution.

## Neyman–Pearson Lemma and Most Powerful Tests

The Neyman–Pearson lemma provides a theoretical foundation for constructing the most powerful test for simple hypotheses. Consider testing

\\[
H_0: \theta = \theta_0 \quad \text{vs.} \quad H_1: \theta = \theta_1
\\]

with likelihood functions \\(L(\theta; X)\\). The lemma states that the test which rejects \\(H_0\\) for large values of the likelihood ratio

\\[
\Lambda(X) = \frac{L(\theta_1; X)}{L(\theta_0; X)}
\\]

is the most powerful test of size \\(\alpha\\). That is, among all tests with Type I error probability \\(\alpha\\), it maximizes power.

## Likelihood Ratio Tests

For composite hypotheses, the **likelihood ratio test (LRT)** generalizes this idea by comparing the maximum likelihood under \\(H_0\\) to the maximum likelihood over the entire parameter space:

\\[
\lambda(X) = \frac{\sup_{\theta \in \Theta_0} L(\theta; X)}{\sup_{\theta \in \Theta} L(\theta; X)}
\\]

where \\(\Theta_0\\) is the parameter space under \\(H_0\\), and \\(\Theta\\) is the full parameter space.

The test rejects \\(H_0\\) for small values of \\(\lambda(X)\\). Under regularity conditions, \\(-2 \log \lambda(X)\\) asymptotically follows a chi-square distribution, enabling approximate significance assessment.

## Role in Scientific Reasoning and Applications

Hypothesis testing plays a crucial role in scientific inquiry by providing a formal mechanism to evaluate claims and quantify uncertainty. It guides decision-making by balancing risks of errors and enabling reproducible conclusions.

In engineering, hypothesis tests underpin quality control, reliability assessment, and system validation. In medicine, they support clinical trials and diagnostic testing. Across disciplines, they form the backbone of empirical validation and inference.
