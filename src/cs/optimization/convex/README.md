# Convex Optimization

A convex optimization problem minimizes a convex function over a convex set. That one structural assumption buys a great deal: every local minimum is global, optimality can be certified by duality, and efficient algorithms come with provable convergence rates. A large part of signal processing, machine learning, control and statistics can be written in this form, from least squares and LASSO to support vector machines, model predictive control and semidefinite relaxations of hard combinatorial problems.

This subsection follows the graduate course *Convex Optimization* (Georgia Tech ECE 6270, Fall 2022). Its emphasis is on algorithms and their analysis, with modeling and duality alongside.

## Chapters

**Foundations**
1. [Convex Optimization Problems and Modeling](modeling.md)
2. [Convex Sets](convex-sets.md)
3. [Convex Functions](convex-functions.md)
4. [Unconstrained Optimality and Line Search](unconstrained.md)

**Unconstrained algorithms**
5. [Gradient Descent and Accelerated Methods](first-order-methods.md)
6. [Newton and Quasi-Newton Methods](newton.md)
7. [Subgradients and Proximal Algorithms](nonsmooth.md)

**Constraints and duality**
8. [Constrained Optimality and the KKT Conditions](constrained-optimality.md)
9. [Lagrange and Fenchel Duality](duality.md)
10. [Algorithms for Constrained Problems](constrained-algorithms.md)

**Large-scale and modern topics**
11. [ADMM and Primal–Dual Splitting](admm.md)
12. [Distributed and Decentralized Optimization](decentralized.md)
13. [Convex Relaxations](relaxations.md)
14. [Stochastic Gradient Methods](stochastic.md)
15. [Minimax Problems and Matrix Games](minimax.md)

## Convergence Rates at a Glance

| Method | Assumptions | Rate |
|---|---|---|
| Gradient descent | \\(L\\)-smooth, convex | \\(O(1/k)\\) |
| Gradient descent | \\(L\\)-smooth, \\(\mu\\)-strongly convex | linear, factor \\(1 - \mu/L\\) |
| Nesterov acceleration | \\(L\\)-smooth, convex | \\(O(1/k^2)\\) |
| Newton's method | strongly convex, Lipschitz Hessian | quadratic (locally) |
| Subgradient method | Lipschitz, convex | \\(O(1/\sqrt{k})\\) |
| Proximal gradient (ISTA / FISTA) | smooth + prox-friendly | \\(O(1/k)\\) / \\(O(1/k^2)\\) |
| SGD | bounded variance, strongly convex | \\(O(1/k)\\) with decreasing steps |

## Related Pages

- [Optimization](../README.md) overview chapters, including [Convex Optimization](../convex.md) and [Gradient Descent and Variants](../gradient.md).
- [Static Optimization](../../../eng/control/optimal-learning/optimization.md) and [Model Predictive Control](../../../eng/control/optimal-learning/mpc.md), where these methods are applied to control.
- [Machine Learning](../../ml/README.md), the largest consumer of first-order and stochastic methods.
