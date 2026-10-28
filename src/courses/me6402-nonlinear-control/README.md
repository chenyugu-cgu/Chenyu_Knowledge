# Nonlinear Control

Real systems are nonlinear: pendulums swing through large angles, actuators saturate, robots have configuration-dependent inertia, and aircraft operate across wide flight envelopes. Linearization explains behavior only near an operating point. Nonlinear control theory studies the whole state space, covering multiple equilibria, limit cycles, finite escape times and regions of attraction, and designs controllers that work there.

The subsection has two parts.

- **Part I** follows the graduate course *Nonlinear Control Systems* (Georgia Tech ME 6402), built on Slotine & Li's *Applied Nonlinear Control*. It covers the core analysis and design toolkit, from phase-plane analysis and Lyapunov theory to feedback linearization, sliding control and adaptive control.
- **Part II** follows the advanced course *Advanced Nonlinear Control* (Georgia Tech AE 8803). It gives a rigorous geometric and Lyapunov-based treatment of stability with inputs, passivity, recursive design, controllability and reduction methods. It ends with a research case study.

## Part I: Analysis and Design

1. [Nonlinear Systems and Their Behavior](phenomena.md)
2. [Phase Plane Analysis](phase-plane.md)
3. [Lyapunov Stability Theory](lyapunov.md)
4. [Invariant Sets, Barbalat's Lemma and Non-Autonomous Systems](invariance.md)
5. [Describing Function Analysis](describing-function.md)
6. [Feedback Linearization](feedback-linearization.md)
7. [Sliding Control](sliding-control.md)
8. [Adaptive Control](adaptive-control.md)
9. [Control of Multi-Input Physical Systems](multi-input.md)

## Part II: Advanced Nonlinear Control

10. [Lyapunov Theory: Advanced Topics](lyapunov-advanced.md)
11. [Input-to-State Stability](iss.md)
12. [Passivity and Dissipativity](passivity.md)
13. [Backstepping and Forwarding](backstepping.md)
14. [Differential Geometry for Nonlinear Control](differential-geometry.md)
15. [Nonlinear Controllability and Stabilizability](controllability.md)
16. [Control Lyapunov Functions](clf.md)
17. [Homogeneous Systems](homogeneity.md)
18. [Center Manifold Theory](center-manifold.md)
19. [Averaging and Singular Perturbations](averaging.md)
20. [Case Study: Shape Control of a Soft Manipulator Suspended from a Quadrotor](cosserat-case-study.md)

## Reading Paths

- **A first course.** Chapters 1–4, then 6–8. Lyapunov's direct method is the thread that runs through stability analysis and every design method.
- **Robotics and mechanical systems.** Chapters 3, 4, 7, 8 and 9, then 12 (passivity) and 13 (backstepping).
- **Theory.** Chapters 10–19 in order. Chapter 14 supplies the geometry that underlies feedback linearization (6) and controllability (15).

## Related Subsections

- [Linear Systems Theory](../me6401-linear-control/README.md): the linear results that nonlinear theory generalizes.
- [Optimal and Learning Control](../ae8803-optimal-learning-control/README.md): optimal and learning-based control for nonlinear systems.
- Robot Control: applications to manipulators.
