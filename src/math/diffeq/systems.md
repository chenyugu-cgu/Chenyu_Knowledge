# Systems of ODEs

Many problems involve several coupled unknowns — predator–prey, coupled masses, chemical reactions, state-space control. These form a **system** of first-order ODEs, written compactly in matrix form.

## Matrix Form

Any higher-order ODE can be rewritten as a first-order system. A linear system is
\\[
\dot{\mathbf{x}} = A\mathbf{x} + \mathbf{b}(t), \qquad \mathbf{x}\in\mathbb{R}^n.
\\]
This is exactly the [state-space](../../eng/control/state-space.md) form used in control.

## Solution by Eigenvalues

For the homogeneous system \\(\dot{\mathbf{x}} = A\mathbf{x}\\), each eigenpair \\((\lambda_i, \mathbf{v}_i)\\) of \\(A\\) gives a mode \\(\mathbf{v}_i e^{\lambda_i t}\\), and the general solution is their superposition:
\\[
\mathbf{x}(t) = \sum_i c_i \mathbf{v}_i e^{\lambda_i t}.
\\]
Equivalently \\(\mathbf{x}(t) = e^{At}\mathbf{x}(0)\\), using the **matrix exponential**. See [Eigenvalues and Eigenvectors](../linear-algebra/eigen.md).

## Stability and Phase Portraits

The eigenvalues classify the equilibrium at the origin:

| Eigenvalues | Behavior |
|---|---|
| All \\(\operatorname{Re}\lambda < 0\\) | stable (sink) |
| Any \\(\operatorname{Re}\lambda > 0\\) | unstable (source/saddle) |
| Pure imaginary | center (oscillation) |
| Complex with \\(\operatorname{Re}\lambda<0\\) | stable spiral |

A **phase portrait** plots trajectories in the state plane, revealing this geometry at a glance.

## Nonlinear Systems

Nonlinear systems are analyzed by **linearizing** about each equilibrium (Jacobian \\(\partial f/\partial x\\)) and applying the eigenvalue test locally — the basis of [linearization in control](../../eng/control/modeling.md). Global behavior (limit cycles, chaos) needs further tools (Lyapunov functions, numerical integration).

## Worked Example: Coupled Decay

\\(\dot{x} = -2x + y,\ \dot{y} = x - 2y\\) has \\(A = \begin{bmatrix}-2&1\\1&-2\end{bmatrix}\\), eigenvalues \\(-1, -3\\) — both negative, so the origin is a stable node; all solutions decay to zero.

## See Also

- [Eigenvalues and Eigenvectors](../linear-algebra/eigen.md)
- [State-Space Representation](../../eng/control/state-space.md)
- [Ordinary Differential Equations (numerical)](../numerical/odes.md)
