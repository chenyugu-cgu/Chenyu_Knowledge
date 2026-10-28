# Random Processes

A random process is a collection of random variables indexed by time or space: the noise in a receiver, the queue at a server, the position of a diffusing particle, the next character typed by a monkey at a keyboard. This subsection develops probability from its axioms up to processes. It covers discrete-time chains and sequences, the Bernoulli and Poisson processes, power spectra, optimal linear estimation (Wiener filtering and prediction), and continuous-time processes such as white Gaussian noise, shot noise and the Wiener process.

It follows the graduate course *Random Processes* (Georgia Tech ECE 6601, Fall 2025). The basic chapters under [Probability and Statistics](../probability/README.md) give a lighter introduction to the first few topics.

## Chapters

**Probability and random variables**
1. [Probability Foundations](probability.md)
2. [Random Variables and Their Distributions](random-variables.md)
3. [Pairs and Vectors of Random Variables](random-vectors.md)
4. [Iterated Expectation and Limit Theorems](limit-theorems.md)

**Random processes**
5. [Bernoulli and Poisson Processes](bernoulli-poisson.md)
6. [Markov Chains](markov-chains.md)
7. [Random Sequences, Stationarity and Power Spectra](random-sequences.md)
8. [Optimal Linear Estimation: MMSE, Wiener Filtering and Prediction](estimation.md)
9. [Continuous-Time Random Processes](continuous-time.md)

## Related Pages

- [Probability and Statistics](../probability/README.md) for introductory material.
- [Signals and Systems](../../signals/fundamentals.md) for the deterministic counterparts of convolution and spectra.
- [Optimal Estimation and the Kalman Filter](../../eng/control/linear/kalman-filter.md), the state-space generalization of Wiener filtering.
