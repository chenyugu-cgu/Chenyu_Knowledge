
# Root Finding

## Theoretical Foundations

### The Root-Finding Problem

The root-finding problem is the task of determining the values of \\(x\\) for which a given function \\(f : D \\to \\mathbb{R}\\) or \\(f : D \\to \\mathbb{C}\\) satisfies \\(f(x) = 0\\), where \\(D\\) is a subset of \\(\\mathbb{R}\\) or \\(\\mathbb{C}\\). The set of all such solutions is called the set of roots or zeros of \\(f\\):
\\[
\\{x \\in D : f(x) = 0\\}
\\]
Root-finding is a central problem in numerical analysis, as many mathematical, physical, and engineering problems reduce to finding roots of equations.

### Existence of Roots: Intermediate Value Theorem

The existence of roots can, in some cases, be established by the Intermediate Value Theorem (IVT). If \\(f : [a, b] \\to \\mathbb{R}\\) is continuous and \\(f(a) \\cdot f(b) < 0\\), then there exists \\(c \\in (a, b)\\) such that \\(f(c) = 0\\). That is,
\\[
\\text{If } f \\text{ is continuous on } [a, b] \\text{ and } f(a) f(b) < 0, \\text{ then } \\exists c \\in (a, b) \\text{ with } f(c) = 0.
\\]
This theorem provides a guarantee for the existence (but not uniqueness) of a root in the interval \\([a, b]\\).

### Iterative Methods and Convergence

Most root-finding algorithms are iterative, producing a sequence \\(\\{x\\_n\\}\\) intended to converge to a root \\(x^\\ast\\) such that \\(f(x^\\ast) = 0\\). The concept of convergence is characterized by:

- **Order of convergence:** The sequence \\(\\{x\\_n\\}\\) converges to \\(x^\\ast\\) with order \\(p > 1\\) if there exists \\(C > 0\\) such that
\\[
\\lim\_{n \\to \\infty} \\frac{|x\\_{n+1} - x^\\ast|}{|x\\_n - x^\\ast|^p} = C.
\\]
  - Linear convergence: \\(p = 1\\).
  - Superlinear: \\(p > 1\\).
  - Quadratic: \\(p = 2\\).
- **Local vs. global convergence:** Local convergence means convergence is guaranteed only if the initial guess is sufficiently close to the root. Global convergence ensures convergence from any starting point in a specified domain.

### Bisection Method

The bisection method is a bracketing method that applies the IVT. Given a continuous function \\(f\\) on \\([a, b]\\) with \\(f(a) f(b) < 0\\), the method repeatedly bisects the interval and selects the subinterval where the sign change occurs. At each iteration, the interval length is halved, and the midpoint is used to test for the sign change:
\\[
m = \\frac{a + b}{2}
\\]
If \\(f(a) f(m) < 0\\), set \\(b = m\\); otherwise, set \\(a = m\\). The process is repeated until the interval is sufficiently small.
- **Convergence guarantee:** The bisection method always converges to a root in \\([a, b]\\) if \\(f\\) is continuous and \\(f(a) f(b) < 0\\).
- **Order of convergence:** Linear (\\(p = 1\\)), with error decreasing by a factor of \\(1/2\\) per iteration.
- **Limitations:** Slow convergence; requires knowledge of an interval with a sign change.

### Newton–Raphson Method

The Newton–Raphson method is an iterative method based on linear approximation via the Taylor expansion. For a differentiable function \\(f\\), the method constructs the tangent line at \\(x\\_n\\):
\\[
f(x) \\approx f(x\\_n) + f'(x\\_n) (x - x\\_n)
\\]
Setting \\(f(x) = 0\\) and solving for \\(x\\) yields the iteration:
\\[
x\\_{n+1} = x\\_n - \\frac{f(x\\_n)}{f'(x\\_n)}
\\]
- **Quadratic convergence:** If \\(f\\) is sufficiently smooth and the initial guess \\(x\\_0\\) is close to a simple root \\(x^\\ast\\), the sequence converges quadratically (\\(p = 2\\)).
- **Dependence on derivative:** Requires evaluation of \\(f'(x)\\). Failure or inaccuracy in computing the derivative can lead to divergence.
- **Sensitivity to initial guess:** Convergence is local; poor initial guesses may lead to divergence or convergence to an unintended root.

### Secant Method

The secant method approximates the derivative in the Newton–Raphson method by using two previous iterates:
\\[
x\\_{n+1} = x\\_n - f(x\\_n) \\frac{x\\_n - x\\_{n-1}}{f(x\\_n) - f(x\\_{n-1})}
\\]
This replaces \\(f'(x\\_n)\\) with a finite difference approximation.
- **Superlinear convergence:** The order of convergence is approximately \\(p \\approx 1.618\\) (the golden ratio), faster than linear but slower than quadratic.
- **No derivative required:** Useful when \\(f'(x)\\) is unavailable or expensive to compute.

### Fixed-Point Iteration

Root-finding can be reformulated as a fixed-point problem: find \\(x\\) such that \\(x = g(x)\\) for an appropriate function \\(g\\). The iteration is:
\\[
x\\_{n+1} = g(x\\_n)
\\]
The Banach fixed-point theorem (contraction mapping theorem) provides conditions for convergence:
- If \\(g : D \\to D\\) is a contraction (i.e., there exists \\(0 < \\lambda < 1\\) such that \\(|g(x) - g(y)| \\leq \\lambda |x - y|\\) for all \\(x, y \\in D\\)), then \\(g\\) has a unique fixed point in \\(D\\), and the iteration converges to it for any initial guess in \\(D\\).

### Practical Considerations

- **Stopping criteria:** Iterations are typically terminated when \\(|x\\_{n+1} - x\\_n|\\) or \\(|f(x\\_{n+1})|\\) falls below a prescribed tolerance.
- **Numerical stability:** Some methods may suffer from loss of significance or amplification of rounding errors, especially near multiple roots or when derivatives are small.
- **Sensitivity to initial guesses:** Methods with local convergence (e.g., Newton–Raphson) require good initial approximations. Poor choices may lead to divergence or convergence to an unintended root.

### Applications

Root-finding methods are fundamental in:
- **Engineering:** Solving nonlinear circuit equations, equilibrium conditions, control system analysis.
- **Physics:** Finding energy eigenvalues, solving transcendental equations, determining critical points.
- **Computational mathematics:** Polynomial equation solving, nonlinear optimization (via stationary points), and as subroutines in numerical integration and differential equation solvers.
