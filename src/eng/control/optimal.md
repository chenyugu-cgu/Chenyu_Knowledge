# Optimal Control

Optimal control chooses the input that **minimizes a cost** while satisfying the system dynamics. Instead of placing poles by intuition, we specify what we care about (energy, error, time) and let optimization find the controller.

## The Optimal Control Problem

Minimize a cost functional subject to the dynamics:
\\[
J = \phi(\mathbf{x}(t_f)) + \int_{t_0}^{t_f} L(\mathbf{x}, \mathbf{u}, t)\,dt
\quad\text{s.t.}\quad \dot{\mathbf{x}} = f(\mathbf{x},\mathbf{u},t).
\\]

## The Linear–Quadratic Regulator (LQR)

For a linear system and quadratic cost,
\\[
J = \int_0^\infty \big(\mathbf{x}^T Q \mathbf{x} + \mathbf{u}^T R \mathbf{u}\big)\,dt,
\quad Q \succeq 0,\ R \succ 0,
\\]
the optimal control is **linear state feedback** \\(\mathbf{u} = -K\mathbf{x}\\) with
\\[
K = R^{-1}B^T P,
\\]
where \\(P\\) solves the **algebraic Riccati equation**
\\[
A^T P + P A - P B R^{-1} B^T P + Q = 0.
\\]
\\(Q\\) penalizes state deviation, \\(R\\) penalizes control effort; their ratio trades performance against actuation.

## The Kalman Filter (LQE)

The dual problem — optimal **estimation** in noise — gives the Kalman filter, which minimizes the estimate error covariance for Gaussian process and measurement noise. It has the observer structure with an optimal gain from a Riccati equation.

## LQG Control

Combining LQR with a Kalman filter gives **Linear–Quadratic–Gaussian (LQG)** control: optimal output-feedback control for noisy linear systems, again justified by the separation principle.

## Pontryagin and Dynamic Programming

- **Pontryagin's Maximum Principle** gives necessary conditions via the Hamiltonian \\(H = L + \boldsymbol{\lambda}^T f\\) and costate equations — handles input constraints (e.g. bang-bang time-optimal control).
- **Bellman's dynamic programming** yields the Hamilton–Jacobi–Bellman (HJB) equation and underlies [reinforcement learning](../../cs/ml/rl.md).

## Model Predictive Control (MPC)

MPC solves a finite-horizon optimal control problem **online** at each step, applies the first input, and repeats (receding horizon). It naturally handles constraints on states and inputs and is now standard in process control, automotive, and robotics.

## See Also

- [Modern Control](modern.md)
- [Constrained Optimization](../../cs/optimization/constrained.md)
- [Reinforcement Learning](../../cs/ml/rl.md)
