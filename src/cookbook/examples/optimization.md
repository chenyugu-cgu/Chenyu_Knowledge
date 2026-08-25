# Optimization Recipes

Runnable recipes for the most common optimization tasks.

---

## Recipe 1 — Gradient Descent from Scratch

**Purpose.** Minimize a smooth function by following the negative gradient.

**Background.** Iterate \\(\mathbf{x}_{k+1} = \mathbf{x}_k - \alpha\nabla f(\mathbf{x}_k)\\). See [Gradient Descent and Variants](../../cs/optimization/gradient.md).

**Example (Python).**
```python
import numpy as np

def gd(grad, x0, lr=0.1, steps=1000, tol=1e-9):
    x = np.array(x0, float)
    for _ in range(steps):
        g = grad(x)
        x_new = x - lr*g
        if np.linalg.norm(x_new - x) < tol:
            break
        x = x_new
    return x

# Minimize f(x,y) = (x-1)^2 + (y+2)^2
grad = lambda v: np.array([2*(v[0]-1), 2*(v[1]+2)])
print(gd(grad, [0, 0]))     # ≈ [1, -2]
```

**Example (Rust, runnable).**
```rust
fn main() {
    // Minimize f(x) = (x - 3)^2 + 2 ; grad = 2(x - 3)
    let (mut x, lr) = (0.0_f64, 0.1_f64);
    for _ in 0..1000 {
        let grad = 2.0 * (x - 3.0);
        let x_new = x - lr * grad;
        if (x_new - x).abs() < 1e-12 {
            break;
        }
        x = x_new;
    }
    println!("argmin ≈ {:.6}, f = {:.6}", x, (x - 3.0).powi(2) + 2.0); // ≈ 3.0, 2.0
}
```

**Result.** Converges to the minimizer; the Rust example finds \\(x \approx 3\\), \\(f \approx 2\\).

**Variations.** Add momentum or use Adam for ill-conditioned problems; use a line search for the step size.

---

## Recipe 2 — Constrained Optimization with SciPy

**Purpose.** Minimize subject to equality/inequality constraints.

**Background.** `scipy.optimize.minimize` with SLSQP handles smooth constrained NLPs via the KKT conditions. See [Constrained Optimization](../../cs/optimization/constrained.md).

**Example (Python).**
```python
from scipy.optimize import minimize

# minimize x^2 + y^2  subject to  x + y = 1,  x >= 0
obj = lambda v: v[0]**2 + v[1]**2
cons = [{"type": "eq", "fun": lambda v: v[0] + v[1] - 1}]
bounds = [(0, None), (None, None)]
res = minimize(obj, [0.5, 0.5], constraints=cons, bounds=bounds)
print("x* =", res.x.round(3), " f* =", round(res.fun, 3))   # [0.5 0.5], 0.5
```

**Result.** Optimum at \\((0.5, 0.5)\\), \\(f^* = 0.5\\) — the closest feasible point to the origin.

**Variations.** Add inequality constraints; compare SLSQP, trust-constr, and interior-point methods.

---

## Recipe 3 — Least Squares Curve Fitting

**Purpose.** Fit a nonlinear model to data by minimizing squared residuals.

**Background.** Nonlinear least squares (Levenberg–Marquardt) minimizes \\(\sum (y_i - f(x_i;\theta))^2\\). See [Unconstrained Optimization](../../cs/optimization/unconstrained.md).

**Example (Python).**
```python
import numpy as np
from scipy.optimize import curve_fit

rng = np.random.default_rng(0)
model = lambda x, a, b, c: a*np.exp(-b*x) + c
x = np.linspace(0, 4, 50)
y = model(x, 2.5, 1.3, 0.5) + 0.05*rng.normal(size=x.size)

params, _ = curve_fit(model, x, y, p0=[1, 1, 0])
print("fitted a,b,c =", params.round(2))    # ≈ [2.5, 1.3, 0.5]
```

**Result.** Recovers the true parameters within noise.

**Variations.** Provide analytic Jacobians for speed; add bounds; use robust loss for outliers.

## References

- [Unconstrained Optimization](../../cs/optimization/unconstrained.md)
- [Constrained Optimization](../../cs/optimization/constrained.md)
- [Convex Optimization](../../cs/optimization/convex.md)
