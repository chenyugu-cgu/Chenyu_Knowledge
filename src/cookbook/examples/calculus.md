# Calculus Recipes

Worked, runnable recipes for the everyday numerical-calculus tasks: finding roots, differentiating, and integrating when closed forms are out of reach.

---

## Recipe 1 — Find a Root with Newton's Method

**Purpose.** Solve \\(f(x) = 0\\) for a smooth nonlinear function.

**Background.** Newton–Raphson iterates the tangent-line update
\\[
x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)},
\\]
converging quadratically near a simple root. See [Root Finding](../../math/numerical/root-finding.md).

**Ingredients.** \\(f\\), its derivative \\(f'\\), an initial guess \\(x_0\\), a tolerance.

**Method.**
1. Evaluate \\(f(x_n)\\) and \\(f'(x_n)\\).
2. Update \\(x_{n+1} = x_n - f/f'\\).
3. Stop when \\(|x_{n+1}-x_n| < \text{tol}\\) or \\(|f| < \text{tol}\\).

**Example (Python).**
```python
def newton(f, df, x0, tol=1e-10, max_iter=100):
    x = x0
    for _ in range(max_iter):
        fx = f(x)
        if abs(fx) < tol:
            break
        x -= fx / df(x)
    return x

# sqrt(2) is the positive root of x^2 - 2
print(newton(lambda x: x*x - 2, lambda x: 2*x, x0=1.0))  # 1.4142135623...
```

**Example (Rust, runnable).**
```rust
fn newton<F, D>(f: F, df: D, x0: f64, tol: f64) -> f64
where
    F: Fn(f64) -> f64,
    D: Fn(f64) -> f64,
{
    let mut x = x0;
    for _ in 0..100 {
        let fx = f(x);
        if fx.abs() < tol {
            break;
        }
        x -= fx / df(x);
    }
    x
}

fn main() {
    let root = newton(|x| x * x - 2.0, |x| 2.0 * x, 1.0, 1e-12);
    println!("sqrt(2) ≈ {:.10}", root); // 1.4142135624
}
```

**Result.** Converges to \\(\sqrt{2} \approx 1.41421356\\) in ~5 iterations.

**Variations.** Use the **secant method** when \\(f'\\) is unavailable; **bisection** for guaranteed (if slower) convergence on a bracketed root.

---

## Recipe 2 — Numerical Differentiation

**Purpose.** Estimate \\(f'(x)\\) from function values alone.

**Background.** The **central difference** is second-order accurate:
\\[
f'(x) \approx \frac{f(x+h) - f(x-h)}{2h}.
\\]

**Example (Python).**
```python
def derivative(f, x, h=1e-5):
    return (f(x + h) - f(x - h)) / (2 * h)

import math
print(derivative(math.sin, 0.0))   # ≈ cos(0) = 1.0
```

**Result.** Error scales as \\(O(h^2)\\); choose \\(h \approx 10^{-5}\\) to balance truncation and round-off.

**Variations.** Use complex-step differentiation \\(\operatorname{Im}[f(x+ih)]/h\\) for round-off-free derivatives; automatic differentiation for exact gradients.

---

## Recipe 3 — Numerical Integration

**Purpose.** Approximate \\(\int_a^b f(x)\,dx\\).

**Background.** **Simpson's rule** fits parabolas and is exact for cubics:
\\[
\int_a^b f\,dx \approx \frac{h}{3}\Big[f_0 + 4\!\!\sum_{\text{odd}}\!f_i + 2\!\!\sum_{\text{even}}\!f_i + f_n\Big].
\\]
See [Numerical Integration](../../math/numerical/integration.md).

**Example (Python).**
```python
import numpy as np
from scipy.integrate import simpson

x = np.linspace(0, np.pi, 101)
print(simpson(np.sin(x), x=x))   # ≈ 2.0  (exact integral of sin over [0, pi])
```

**Result.** Returns ≈ 2.0, accurate to machine precision for smooth integrands.

**Variations.** Use Gaussian quadrature for higher accuracy with fewer points; adaptive quadrature (`scipy.integrate.quad`) for difficult integrands.

## References

- [Limits and Continuity](../../math/calculus/limits.md)
- [Integration](../../math/calculus/integration.md)
- [Root Finding](../../math/numerical/root-finding.md)
