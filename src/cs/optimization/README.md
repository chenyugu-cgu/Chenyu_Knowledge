# Optimization

Optimization is the art of finding the **best** solution — minimizing cost, maximizing performance, fitting models — subject to constraints. It underpins machine learning, control, operations research, and engineering design.

## The General Problem

\\[
\min_{\mathbf{x}\in\mathbb{R}^n} f(\mathbf{x}) \quad\text{subject to}\quad
g_i(\mathbf{x}) \le 0,\quad h_j(\mathbf{x}) = 0.
\\]
Here \\(f\\) is the **objective**, the \\(g_i\\) are **inequality constraints**, and the \\(h_j\\) are **equality constraints**. The set of points satisfying all constraints is the **feasible region**.

## A Taxonomy

| Property | Classes |
|---|---|
| Constraints | unconstrained vs. constrained |
| Convexity | convex (global optimum) vs. nonconvex (local optima) |
| Smoothness | differentiable vs. nonsmooth |
| Variables | continuous vs. integer/combinatorial |
| Information | gradient-based vs. derivative-free |

Convexity is the great dividing line: convex problems have a single global optimum reachable efficiently; nonconvex problems may trap algorithms in local optima.

## Optimality Conditions

For a smooth unconstrained problem, a minimum requires
\\[
\nabla f(\mathbf{x}^*) = \mathbf{0} \quad(\text{first-order}), \qquad \nabla^2 f(\mathbf{x}^*) \succeq 0 \quad(\text{second-order}).
\\]
Constrained problems add the **KKT conditions** (see [Constrained Optimization](constrained.md)).

## Chapter Map

- [Unconstrained Optimization](unconstrained.md)
- [Constrained Optimization](constrained.md)
- [Convex Optimization](convex.md)
- [Gradient Descent and Variants](gradient.md)
- [Metaheuristic Methods](metaheuristics.md)

Optimization is the engine behind [Machine Learning](../ml/README.md) and [Optimal Control](../../eng/control/optimal.md).
