# Information Theory

Information theory, founded by Claude Shannon in 1948, quantifies **information**, **compression**, and **communication**. It sets the fundamental limits on how much data can be compressed and how fast it can be transmitted reliably — and its central quantity, entropy, recurs across [ML](../ml/README.md), [physics](../../physics/modern/statistical-mechanics.md), and biology.

## The Big Questions

1. How much information does a source produce? → **entropy** ([Entropy and Information](entropy.md)).
2. How much can we compress it? → **source coding** ([Source Coding](source-coding.md)).
3. How fast can we communicate reliably over a noisy channel? → **channel capacity** ([Channel Capacity](channel-capacity.md)).

## The Central Idea

Information is **surprise**. A certain event carries none; a rare event carries a lot. Shannon made this precise: the information of an event of probability \\(p\\) is \\(-\log_2 p\\) bits, and **entropy** is its expected value.

## Chapter Map

- [Entropy and Information](entropy.md)
- [Source Coding](source-coding.md)
- [Channel Capacity](channel-capacity.md)

## Connections

Entropy links to [thermodynamics](../../physics/modern/statistical-mechanics.md) (Boltzmann's \\(S = k\ln\Omega\\)), to [ML](../ml/evaluation.md) (cross-entropy loss, mutual information), and to [signals](../../signals/sampling.md) (sampling and rate). Cross-entropy and KL divergence are everyday tools in machine learning.

## See Also

- [Distributions](../../math/probability/distributions.md)
- [Statistical Mechanics](../../physics/modern/statistical-mechanics.md)
