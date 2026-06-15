# Convex Optimization

Convex optimization is the most important "easy" class of problems: every local minimum is **global**, and efficient algorithms find it reliably. Recognizing or reformulating a problem as convex is often the single most valuable modeling skill.

## Convex Sets and Functions

A set \\(C\\) is **convex** if the segment between any two points stays in \\(C\\): \\(\theta x + (1-\theta)y \in C\\) for \\(\theta\in[0,1]\\).

A function \\(f\\) is **convex** if
\\[
f(\theta x + (1-\theta)y) \le \theta f(x) + (1-\theta)f(y).
\\]
Equivalently (when twice differentiable) its Hessian is positive semidefinite, \\(\nabla^2 f \succeq 0\\). The graph lies below its chords and above its tangents.

## Why Convexity Matters

- **Any local minimum is global.**
- The **KKT conditions are sufficient** for optimality.
- Polynomial-time interior-point algorithms solve large instances reliably.
- **Duality** is strong (no gap) under mild conditions.

## Standard Problem Classes

| Class | Form |
|---|---|
| Linear program (LP) | linear objective & constraints |
| Quadratic program (QP) | convex quadratic objective, linear constraints |
| Second-order cone (SOCP) | norms in constraints |
| Semidefinite program (SDP) | matrix-PSD constraints |

These nest: LP ⊂ QP ⊂ SOCP ⊂ SDP, all solvable by the same interior-point machinery.

## Duality

Every problem has a **dual**, formed from the Lagrangian:
\\[
g(\boldsymbol{\lambda},\boldsymbol{\mu}) = \inf_{\mathbf{x}}\, \mathcal{L}(\mathbf{x},\boldsymbol{\lambda},\boldsymbol{\mu}).
\\]
**Weak duality** \\(g(\lambda,\mu) \le f(x)\\) always holds; **strong duality** (equality) holds for convex problems under Slater's condition. The dual provides certificates of optimality and bounds.

## Modeling in Practice

```python
import cvxpy as cp
import numpy as np

# Least squares with a non-negativity constraint
A = np.random.randn(50, 10)
b = np.random.randn(50)
x = cp.Variable(10)
prob = cp.Problem(cp.Minimize(cp.sum_squares(A @ x - b)), [x >= 0])
prob.solve()
print("optimal value:", round(prob.value, 4))
```

Disciplined convex programming (DCP) tools like CVXPY let you state the problem declaratively and guarantee convexity by construction.

## See Also

- [Constrained Optimization](constrained.md)
- [Gradient Descent and Variants](gradient.md)
- [Regularization](../ml/regularization.md) — Lasso/Ridge are convex programs.
