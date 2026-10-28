# Optimal and Learning Control

Optimal control asks for the *best* control, the one that minimizes a cost such as energy, time or tracking error, subject to the system's dynamics and constraints. It connects the calculus of variations, Pontryagin's minimum principle and Bellman's dynamic programming. Its most celebrated product is the linear quadratic regulator. When the model is unknown, the same Bellman equations become the foundation of reinforcement learning and adaptive dynamic programming. When several decision makers interact, they become games.

This subsection follows the graduate course *Optimization-Based Learning Control and Games* (Georgia Tech AE 8803). It adds two chapters on model predictive control, drawn from the recorded lectures of a graduate MPC course (Duke ME 555, 2023).

## Chapters

**Optimization foundations**
1. [Static Optimization](optimization.md)
2. [Calculus of Variations and the Riccati Equation](calculus-of-variations.md)

**Optimal control**
3. [Discrete-Time Optimal Control and LQR](discrete-optimal-control.md)
4. [Continuous-Time Optimal Control and Two-Point Boundary-Value Problems](continuous-optimal-control.md)
5. [Continuous-Time LQR and Its Extensions](continuous-lqr.md)
6. [Pontryagin's Minimum Principle](pontryagin.md)
7. [Dynamic Programming and the Hamilton–Jacobi–Bellman Equation](dynamic-programming.md)

**Learning, games and receding horizon**
8. [Reinforcement Learning and Adaptive Dynamic Programming](reinforcement-learning.md)
9. [Dynamic and Differential Games](games.md)
10. [Model Predictive Control: Formulation and Solution](mpc.md)
11. [Invariant Sets, Recursive Feasibility and Stability of MPC](mpc-stability.md)

## Three Routes to the Same Answer

For the linear quadratic problem, the three classical approaches agree:

| Route | Central object | Gives |
|---|---|---|
| Calculus of variations / minimum principle | Hamiltonian \\(H = L + \lambda^T f\\), costate \\(\lambda\\) | Necessary conditions; a two-point boundary-value problem |
| Sweep method | \\(\lambda(t) = P(t)x(t)\\) | The differential Riccati equation |
| Dynamic programming | Value function \\(V(x,t) = x^TP(t)x\\) | The Hamilton–Jacobi–Bellman equation, which reduces to the same Riccati equation |

Reinforcement learning solves the Bellman equation from data instead of from a model. Model predictive control re-solves a finite-horizon optimal control problem at every sample and applies only the first move.

## Related Subsections

- [Linear Systems Theory](../me6401-linear-control/README.md): LQR, the Kalman filter and LQG from the linear-systems viewpoint.
- [Digital Control](../me6403-digital-control/README.md): discrete LQR and an introduction to RL for control.
- Optimization and Reinforcement Learning elsewhere in the book.
