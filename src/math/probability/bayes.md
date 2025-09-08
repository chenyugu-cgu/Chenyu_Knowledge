# Bayesian Inference

Bayesian inference is a fundamental statistical paradigm that interprets probability as a measure of belief or certainty about events or parameters, updated in light of new evidence. At its core lies Bayes' theorem, which provides a formal mechanism to revise prior beliefs given observed data.

Bayes' theorem states that for events \\(A\\) and \\(B\\) with \\(P(B) > 0\\),

\\[
P(A \mid B) = \frac{P(B \mid A) \, P(A)}{P(B)} \,,
\\]

where \\(P(A)\\) is the prior probability of \\(A\\), \\(P(B \mid A)\\) is the likelihood of observing \\(B\\) given \\(A\\), \\(P(B)\\) is the marginal likelihood or evidence, and \\(P(A \mid B)\\) is the posterior probability of \\(A\\) after observing \\(B\\).

In the context of statistical inference, \\(A\\) often represents a hypothesis or parameter value \\(\theta\\), and \\(B\\) represents observed data \\(D\\). The prior distribution \\(P(\theta)\\) encodes our initial beliefs about \\(\theta\\) before seeing data. The likelihood function \\(P(D \mid \theta)\\) expresses the probability of the observed data given the parameter. The posterior distribution

\\[
P(\theta \mid D) = \frac{P(D \mid \theta) \, P(\theta)}{P(D)}
\\]

represents the updated beliefs after incorporating the data. The evidence \\(P(D) = \int P(D \mid \theta) P(\theta) \, d\theta\\) serves as a normalizing constant ensuring the posterior sums or integrates to one.

A crucial concept in Bayesian inference is the choice of prior distribution. When the prior and posterior distributions belong to the same family, the prior is called a conjugate prior. Conjugacy facilitates analytical tractability, allowing closed-form expressions for the posterior. For example, a Beta prior is conjugate to the Bernoulli likelihood, yielding a Beta posterior. This property simplifies updating beliefs and computing posterior summaries.

Bayesian updating is inherently sequential: as new data \\(D_1, D_2, \ldots, D_n\\) arrive, the posterior after observing \\(D_1, \ldots, D_{k-1}\\) becomes the prior for the next update with data \\(D_k\\). Formally,

\\[
P(\theta \mid D_1, \ldots, D_k) \propto P(D_k \mid \theta) \, P(\theta \mid D_1, \ldots, D_{k-1}) \,.
\\]

This recursive structure elegantly models learning over time.

In contrast to frequentist confidence intervals, Bayesian credible intervals provide a probability statement about the parameter itself. A \\(100(1-\alpha)\%\\) credible interval \\(\mathcal{C}\\) satisfies

\\[
P(\theta \in \mathcal{C} \mid D) = 1 - \alpha \,,
\\]

meaning there is a \\(1-\alpha\\) probability that \\(\theta\\) lies in \\(\mathcal{C}\\) given the observed data and prior. This interpretation is direct and intuitive, reflecting uncertainty about the parameter rather than about repeated sampling properties.

Bayesian decision theory extends inference to decision making under uncertainty by incorporating loss functions \\(L(\theta, a)\\), which quantify the cost of taking action \\(a\\) when the true parameter is \\(\theta\\). The optimal Bayesian decision minimizes the expected posterior loss,

\\[
a^* = \arg \min_a \int L(\theta, a) \, P(\theta \mid D) \, d\theta \,.
\\]

This framework unifies estimation, hypothesis testing, and prediction within a coherent probabilistic approach.

Applications of Bayesian inference span numerous fields. In statistics, it underpins hierarchical modeling and empirical Bayes methods. In engineering, it is employed in signal processing and control systems for adaptive filtering and fault detection. In machine learning, Bayesian methods provide principled approaches to model selection, regularization, and uncertainty quantification, as seen in Bayesian neural networks, Gaussian processes, and probabilistic graphical models.

Overall, Bayesian inference offers a rigorous and flexible framework for reasoning under uncertainty, combining prior knowledge with observed data to yield updated, probabilistically coherent conclusions.
