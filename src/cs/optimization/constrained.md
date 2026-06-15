# Constrained Optimization

Most real problems have constraints — budgets, capacities, physical limits. Constrained optimization finds the best feasible point.

## The Problem

\\[
\min_{\mathbf{x}} f(\mathbf{x}) \quad\text{s.t.}\quad g_i(\mathbf{x}) \le 0,\quad h_j(\mathbf{x}) = 0.
\\]

## Lagrange Multipliers (equality constraints)

For equality constraints, form the **Lagrangian**
\\[
\mathcal{L}(\mathbf{x}, \boldsymbol{\lambda}) = f(\mathbf{x}) + \sum_j \lambda_j h_j(\mathbf{x}),
\\]
and solve \\(\nabla_{\mathbf{x}}\mathcal{L} = 0,\ \nabla_{\boldsymbol{\lambda}}\mathcal{L} = 0\\). Geometrically, at the optimum the objective gradient is a linear combination of the constraint gradients. The multiplier \\(\lambda_j\\) is the **shadow price** — the sensitivity of the optimum to relaxing constraint \\(j\\).

## KKT Conditions (inequality constraints)

The **Karush–Kuhn–Tucker** conditions generalize Lagrange to inequalities. With multipliers \\(\mu_i \ge 0\\):
\\[
\nabla f + \sum_i \mu_i \nabla g_i + \sum_j \lambda_j \nabla h_j = 0,
\\]
\\[
g_i \le 0, \quad h_j = 0, \quad \mu_i \ge 0, \quad \mu_i g_i = 0\ (\text{complementary slackness}).
\\]
Complementary slackness says each inequality is either active (\\(g_i = 0\\)) or its multiplier is zero. For convex problems, KKT is **necessary and sufficient** for global optimality.

## Linear and Quadratic Programming

- **Linear programming (LP):** linear objective and constraints; solved by the **simplex** method (vertex-walking) or interior-point methods. The optimum lies at a vertex of the feasible polytope.
- **Quadratic programming (QP):** quadratic objective, linear constraints; the workhorse of SVMs and MPC.

## Solution Strategies

- **Penalty methods:** add \\(\rho\sum \max(0, g_i)^2\\) to push iterates toward feasibility.
- **Barrier / interior-point:** add \\(-\mu\sum\log(-g_i)\\) to stay strictly inside; the basis of modern convex solvers.
- **Augmented Lagrangian:** combine multipliers with a penalty for robust convergence.
- **Sequential Quadratic Programming (SQP):** solve a QP approximation each iteration — the standard for smooth nonlinear programs.

## Worked Example

Minimize \\(f = x^2 + y^2\\) subject to \\(x + y = 1\\). The Lagrangian gives \\(2x = 2y = -\lambda\\), so \\(x = y = 1/2\\), \\(f^* = 1/2\\) — the closest point on the line to the origin.

## See Also

- [Convex Optimization](convex.md)
- [Optimal Control](../../eng/control/optimal.md)
- [Supervised Learning](../ml/supervised.md) — SVMs as QPs.
