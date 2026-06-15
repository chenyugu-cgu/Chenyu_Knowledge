# Unconstrained Optimization

Unconstrained optimization minimizes \\(f(\mathbf{x})\\) over all of \\(\mathbb{R}^n\\) with no constraints. It is the core engine inside almost every learning and estimation algorithm.

## Optimality Conditions

At a local minimum \\(\mathbf{x}^*\\) of a smooth function:
\\[
\nabla f(\mathbf{x}^*) = \mathbf{0} \quad(\text{stationary}), \qquad \nabla^2 f(\mathbf{x}^*) \succeq 0 \quad(\text{PSD Hessian}).
\\]
A stationary point is a minimum, maximum, or saddle depending on the Hessian's eigenvalues.

## Descent Methods

Iterative methods take steps \\(\mathbf{x}_{k+1} = \mathbf{x}_k + \alpha_k \mathbf{p}_k\\) along a **descent direction** \\(\mathbf{p}_k\\) (with \\(\nabla f^T \mathbf{p}_k < 0\\)) and a **step size** \\(\alpha_k\\) chosen by line search.

### Steepest Descent

Take \\(\mathbf{p}_k = -\nabla f(\mathbf{x}_k)\\). Simple and robust but slow (zig-zags) on ill-conditioned problems — convergence rate depends on the condition number \\(\kappa\\) of the Hessian. See [Gradient Descent and Variants](gradient.md).

### Newton's Method

Use curvature for quadratic convergence near the optimum:
\\[
\mathbf{x}_{k+1} = \mathbf{x}_k - [\nabla^2 f(\mathbf{x}_k)]^{-1}\nabla f(\mathbf{x}_k).
\\]
Fast but costs \\(O(n^3)\\) per step (solving the Hessian system) and needs the Hessian to be positive definite.

### Quasi-Newton (BFGS)

Approximate the inverse Hessian from successive gradients, achieving superlinear convergence without computing second derivatives. **L-BFGS** stores only a few vectors and scales to large \\(n\\) — the default for many smooth problems.

### Conjugate Gradient

Builds conjugate directions; ideal for large quadratic systems (and linear solves) with only matrix–vector products.

## Line Search

The step size is chosen to ensure sufficient decrease via the **Armijo (backtracking)** condition
\\[
f(\mathbf{x}_k + \alpha\mathbf{p}_k) \le f(\mathbf{x}_k) + c_1\alpha\,\nabla f^T\mathbf{p}_k,
\\]
optionally with the curvature (Wolfe) condition. Trust-region methods are the robust alternative.

## Worked Example: Minimizing the Rosenbrock Function

```python
import numpy as np
from scipy.optimize import minimize

def rosen(x):
    return sum(100*(x[1:]-x[:-1]**2)**2 + (1-x[:-1])**2)

x0 = np.array([-1.2, 1.0])
res = minimize(rosen, x0, method="BFGS")
print("minimum at:", res.x, " f =", round(res.fun, 6))   # ~[1, 1], f ~ 0
```

## See Also

- [Gradient Descent and Variants](gradient.md)
- [Convex Optimization](convex.md)
- [Multivariable Calculus](../../math/calculus/multivariable.md)
