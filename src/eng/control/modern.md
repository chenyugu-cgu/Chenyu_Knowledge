# Modern Control

Modern control works in the **state space** and with matrix methods, enabling design for multivariable, time-varying, and high-order systems beyond the reach of classical single-loop techniques.

## State Feedback and Pole Placement

Given a controllable system \\(\dot{\mathbf{x}} = A\mathbf{x} + B\mathbf{u}\\), full-state feedback \\(\mathbf{u} = -K\mathbf{x}\\) yields closed-loop dynamics \\(\dot{\mathbf{x}} = (A - BK)\mathbf{x}\\). The gain \\(K\\) is chosen so the eigenvalues of \\(A - BK\\) match a desired set, fixing damping and speed. Ackermann's formula computes \\(K\\) directly.

## State Estimation (Observers)

When states are not measured, a **Luenberger observer** reconstructs them:
\\[
\dot{\hat{\mathbf{x}}} = A\hat{\mathbf{x}} + B\mathbf{u} + L(\mathbf{y} - C\hat{\mathbf{x}}).
\\]
The estimation error obeys \\(\dot{\mathbf{e}} = (A - LC)\mathbf{e}\\); choose \\(L\\) (a dual pole-placement problem) so the error decays faster than the controller dynamics.

## Separation Principle

Controller and observer can be designed **independently**: the combined closed-loop eigenvalues are the union of those of \\(A - BK\\) and \\(A - LC\\). This decoupling is what makes observer-based control practical.

## Integral Action and Tracking

Augmenting the state with the integral of the tracking error \\(\dot{x}_I = r - y\\) and feeding it back drives steady-state error to zero — the state-space analogue of integral control.

## Robust and Adaptive Control

- **Robust control** (H∞, μ-synthesis) designs controllers guaranteeing performance despite bounded model uncertainty.
- **Adaptive control** adjusts controller parameters online as the plant changes (MRAC, self-tuning regulators).
- **Gain scheduling** interpolates a family of linear controllers across operating points — standard in aerospace.

## Nonlinear Control

For genuinely nonlinear plants:
- **Feedback linearization** cancels nonlinearities via a coordinate/feedback transformation.
- **Sliding-mode control** forces the state onto a stable manifold, robust to disturbances.
- **Lyapunov methods** prove stability by finding an energy-like function \\(V(\mathbf{x})>0\\) with \\(\dot V < 0\\).

## See Also

- [State-Space Representation](state-space.md)
- [Optimal Control](optimal.md)
- [Robot Control](../../app/robotics/control.md)
