# Linear Systems Theory

Linear systems theory is the backbone of modern control. It describes a system by its state, a vector \\(x(t)\\) that summarizes everything about the past needed to predict the future, and studies the linear state equations
\\[
\dot x = A(t)\\,x + B(t)\\,u, \qquad y = C(t)\\,x + D(t)\\,u
\\]
in depth: how solutions behave, which states can be steered and observed, and how feedback, observers and optimal design follow from that structure.

This subsection follows the graduate course *Linear Control Systems* (Georgia Tech ME 6401). Its main reference is Hespanha's *Linear Systems Theory*, with Chen's *Linear System Theory and Design* and Williams & Lawrence's *Linear State-Space Control Systems* as companions. It is considerably more rigorous than the short overview chapters on State-Space Representation and Modern Control.

## Chapters

**Models and solutions**
1. [Modeling and Linearization of Dynamic Systems](modeling.md)
2. [State Transformations and Canonical Realizations](realizations.md)
3. [Time Response of Linear Systems](time-response.md)
4. [Discrete-Time Linear Systems](discrete-time.md)

**Structure**
5. [Linear Algebra for Systems Theory](linear-algebra.md)
6. [Modal Decomposition and the Jordan Form](modal-decomposition.md)
7. [Stability of Linear Systems](stability.md)
8. [Controllability](controllability.md)
9. [Observability](observability.md)
10. [Structural Decompositions and Minimal Realizations](structure.md)

**Design**
11. [State Feedback and Pole Placement](state-feedback.md)
12. [Observers](observers.md)
13. [Combined Controller–Observer Design](separation.md)
14. [The Linear Quadratic Regulator](lqr.md)
15. [Optimal Estimation and the Kalman Filter](kalman-filter.md)
16. [LQG Control and Loop Transfer Recovery](lqg.md)

## How the Pieces Fit

The course moves from *analysis* to *synthesis*:

- **Analysis.** The solution \\(x(t) = \Phi(t,t\_0)x(t\_0) + \int \Phi(t,\tau)B(\tau)u(\tau)d\tau\\) organizes everything else. Its modes (eigenvalues and Jordan structure) decide stability. The controllability and observability Gramians decide which states the input can reach and which states the output reveals.
- **Synthesis.** If \\((A,B)\\) is controllable, state feedback \\(u = -Kx\\) can place the closed-loop eigenvalues anywhere. If \\((A,C)\\) is observable, an observer can reconstruct \\(x\\) from \\(y\\). The separation principle says the two designs can be done independently.
- **Optimal design.** LQR chooses \\(K\\) optimally and the Kalman filter chooses the observer gain optimally; these are dual problems solved by Riccati equations. Their combination, LQG, needs loop transfer recovery to regain LQR's robustness margins.

## Related Subsections

- [Nonlinear Control](../me6402-nonlinear-control/README.md) extends stability and design to nonlinear systems.
- [Digital Control](../me6403-digital-control/README.md) develops the sampled-data counterparts of these tools.
- [Optimal and Learning Control](../ae8803-optimal-learning-control/README.md) derives LQR from the calculus of variations and dynamic programming, and extends it to learning-based control.
