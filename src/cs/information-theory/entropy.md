# Entropy and Information

Entropy measures the average uncertainty — or information content — of a random source. It is the cornerstone of information theory.

## Self-Information and Entropy

The information of an outcome with probability \\(p\\) is \\(-\log_2 p\\) **bits**. The **entropy** of a discrete random variable is the expected information:
\\[
H(X) = -\sum_i p_i \log_2 p_i.
\\]
Entropy is maximized by a uniform distribution (\\(\log_2 n\\) bits for \\(n\\) equally likely outcomes) and zero for a certain outcome.

**Example.** A fair coin has \\(H = 1\\) bit; a biased coin with \\(p=0.9\\) has \\(H \approx 0.47\\) bits — less surprising, less information.

## Joint, Conditional, and Mutual Information

- **Joint entropy** \\(H(X,Y)\\) — uncertainty of the pair.
- **Conditional entropy** \\(H(Y\mid X)\\) — remaining uncertainty in \\(Y\\) given \\(X\\).
- **Mutual information** measures shared information:
\\[
I(X;Y) = H(X) - H(X\mid Y) = H(X) + H(Y) - H(X,Y) \ge 0.
\\]
\\(I(X;Y)=0\\) iff \\(X\\) and \\(Y\\) are independent. Mutual information is a powerful, model-free measure of dependence used in [feature selection](../ml/features.md).

## Relative Entropy (KL Divergence)

\\[
D_{KL}(p\,\|\,q) = \sum_i p_i\log_2\frac{p_i}{q_i} \ge 0,
\\]
the "extra bits" from coding with the wrong distribution \\(q\\). It is not symmetric and is the basis of the **cross-entropy loss** that trains classifiers (see [Model Evaluation](../ml/evaluation.md)).

## Connections

- **Compression** — entropy is the minimum average bits per symbol (next chapter).
- **Machine learning** — cross-entropy, KL divergence, and information gain (decision trees).
- **Physics** — Shannon entropy mirrors Boltzmann's [thermodynamic entropy](../../physics/modern/statistical-mechanics.md).

## See Also

- [Source Coding](source-coding.md)
- [Statistical Mechanics](../../physics/modern/statistical-mechanics.md)
- [Feature Engineering](../ml/features.md)
