# State-Space Representation

State space describes a system by a set of first-order differential equations in terms of internal **state variables**. It handles multi-input multi-output (MIMO) systems, nonlinearities, and modern control design that transfer functions cannot.

## The State Equations

A continuous LTI system is written
\\[
\dot{\mathbf{x}} = A\mathbf{x} + B\mathbf{u}, \qquad \mathbf{y} = C\mathbf{x} + D\mathbf{u},
\\]
where \\(\mathbf{x}\in\mathbb{R}^n\\) is the state, \\(\mathbf{u}\\) the input, \\(\mathbf{y}\\) the output, and \\((A,B,C,D)\\) are the system matrices. The **state** is the minimal information needed to predict the future given the input.

## From Transfer Function to State Space

An \\(n\\)-th order transfer function maps to \\(n\\) state variables. The **controllable canonical form** places the denominator coefficients in the bottom row of \\(A\\). The map is not unique — any invertible change of variables \\(\mathbf{z}=T\mathbf{x}\\) gives an equivalent realization.

## Solution and the Matrix Exponential

The state response is
\\[
\mathbf{x}(t) = e^{At}\mathbf{x}(0) + \int_0^t e^{A(t-\tau)}B\mathbf{u}(\tau)\,d\tau,
\\]
where the **state-transition matrix** \\(e^{At}\\) is computed from the eigen-decomposition of \\(A\\). The eigenvalues of \\(A\\) **are** the poles of the transfer function.

## Controllability and Observability

Two structural properties decide what control can achieve:

- **Controllable** — the input can drive the state anywhere; the controllability matrix \\(\mathcal{C} = [B\ AB\ \cdots\ A^{n-1}B]\\) has full rank \\(n\\).
- **Observable** — the state can be reconstructed from outputs; the observability matrix \\(\mathcal{O} = [C;\ CA;\ \cdots;\ CA^{n-1}]\\) has full rank \\(n\\).

Controllability is required for pole placement; observability for state estimation.

## Pole Placement

If \\((A,B)\\) is controllable, state feedback \\(\mathbf{u} = -K\mathbf{x}\\) places the closed-loop poles (eigenvalues of \\(A - BK\\)) **anywhere** we choose, setting the desired damping and speed.

## Observers

When the state is not directly measured, a **Luenberger observer** estimates it:
\\[
\dot{\hat{\mathbf{x}}} = A\hat{\mathbf{x}} + B\mathbf{u} + L(\mathbf{y} - C\hat{\mathbf{x}}).
\\]
The **separation principle** lets us design the feedback \\(K\\) and observer \\(L\\) independently.

## See Also

- [Eigenvalues and Eigenvectors](../../math/linear-algebra/eigen.md)
- [Modern Control](modern.md)
- [Optimal Control](optimal.md)
