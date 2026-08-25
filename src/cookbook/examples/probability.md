# Probability Recipes

Runnable recipes for simulation, estimation, and Bayesian reasoning.

---

## Recipe 1 — Estimate π by Monte Carlo

**Purpose.** Estimate an integral / probability by random sampling.

**Background.** The fraction of random points in the unit square that fall inside the quarter circle approximates \\(\pi/4\\). This is the simplest **Monte Carlo** estimator; error shrinks as \\(O(1/\sqrt{N})\\). See [Law of Large Numbers & CLT](../../math/probability/clt.md).

**Ingredients.** A uniform random generator, \\(N\\) samples.

**Method.**
1. Sample \\((x, y)\\) uniformly in \\([0,1]^2\\).
2. Count points with \\(x^2 + y^2 \le 1\\).
3. Multiply the inside fraction by 4.

**Example (Python).**
```python
import numpy as np

rng = np.random.default_rng(0)
N = 1_000_000
pts = rng.random((N, 2))
inside = np.mean(np.sum(pts**2, axis=1) <= 1.0)
print("pi ≈", 4 * inside)        # ≈ 3.1416
```

**Result.** ≈ 3.1416 for \\(N = 10^6\\); accuracy improves with more samples.

**Variations.** Use Monte Carlo to price options, integrate high-dimensional functions, or propagate uncertainty.

---

## Recipe 2 — Bayesian Updating of a Coin's Bias

**Purpose.** Update belief about a probability \\(p\\) after observing data.

**Background.** With a **Beta\\((\alpha,\beta)\\)** prior and a Binomial likelihood, the posterior is **Beta\\((\alpha + k,\ \beta + n - k)\\)** — conjugacy makes the update exact. See [Bayesian Inference](../../math/probability/bayes.md).

**Example (Python).**
```python
from scipy.stats import beta

alpha0, beta0 = 1, 1          # uniform prior
heads, tails = 8, 2           # observed 8 heads in 10 flips
post = beta(alpha0 + heads, beta0 + tails)
print("posterior mean:", round(post.mean(), 3))            # 0.75
print("95% credible interval:", post.interval(0.95))       # (≈0.48, ≈0.94)
```

**Result.** Posterior mean 0.75 with a 95% credible interval; the prior is updated toward the data.

**Variations.** Use MCMC (PyMC, Stan) when no conjugate form exists.

---

## Recipe 3 — Fit a Distribution and Test Goodness of Fit

**Purpose.** Estimate parameters and check whether data follows an assumed distribution.

**Background.** **Maximum likelihood** estimates parameters; a **Kolmogorov–Smirnov** test compares the empirical and fitted CDFs. See [Statistical Estimation](../../math/probability/estimation.md) and [Hypothesis Testing](../../math/probability/hypothesis-testing.md).

**Example (Python).**
```python
import numpy as np
from scipy import stats

rng = np.random.default_rng(1)
data = rng.normal(loc=5, scale=2, size=500)

mu, sigma = stats.norm.fit(data)         # MLE estimates
ks_stat, p = stats.kstest(data, "norm", args=(mu, sigma))
print(f"mu={mu:.2f}, sigma={sigma:.2f}, KS p-value={p:.3f}")
```

**Result.** Recovers \\(\mu \approx 5\\), \\(\sigma \approx 2\\); a large p-value means we cannot reject normality.

**Variations.** Swap in other distributions; use AIC/BIC to compare candidate models.

## References

- [Distributions](../../math/probability/distributions.md)
- [Expectation and Variance](../../math/probability/expectation.md)
- [Bayesian Inference](../../math/probability/bayes.md)
