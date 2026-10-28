# Digital Control

Almost every modern controller is a computer program. It samples sensors at discrete instants, computes, and holds its output constant until the next sample. Digital control studies the resulting sampled-data loop: how to represent continuous plants in discrete time, how sampling changes stability and performance, and how to design controllers directly in the discrete domain.

This subsection follows the graduate course *Digital Control Systems* (Georgia Tech ME 6403), with Fadali & Visioli's *Digital Control Engineering: Analysis and Design* as the main text. The first half is classical (transform-domain) design and the second half is state-space and optimal design, ending with dynamic programming and reinforcement learning.

## Chapters

**Signals and transforms**
1. [Digital Control Systems: Architecture and Hardware](introduction.md)
2. [The z-Transform and Difference Equations](z-transform.md)
3. [Sampling, Reconstruction and Discretization](sampling.md)
4. [Pulse Transfer Functions and z-Plane Analysis](z-plane.md)

**Classical design**
5. [Transient Specifications and the s-to-z Mapping](classical-design.md)
6. [Root-Locus Design of Digital Controllers](root-locus.md)
7. [Frequency-Response Analysis of Digital Systems](frequency-response.md)

**State-space design**
8. [Discrete-Time State-Space Models](state-space.md)
9. [State Feedback and Pole Placement for Discrete Systems](state-feedback.md)
10. [Observers for Discrete Systems](observers.md)
11. [Combined Controller–Observer Design](controller-observer.md)
12. [Tracking and Disturbance Rejection](tracking.md)
13. [Discrete-Time Linear Quadratic Regulation](lqr.md)
14. [Dynamic Programming and Reinforcement Learning for Control](reinforcement-learning.md)

## The Central Idea

The map \\(z = e^{sT}\\) links the two worlds. The left half of the s-plane maps into the unit disk, a constant damping ratio becomes a logarithmic spiral, and the sampling period \\(T\\) decides how much of the s-plane can be represented without aliasing. Almost every design rule in this subsection is a continuous-time rule transported through that map, plus a correction for what the zero-order hold and the computation delay add.

## Related Subsections

- [Linear Systems Theory](../me6401-linear-control/README.md): the continuous-time state-space theory.
- The Z-Transform and Sampling and Reconstruction: signal-processing background.
- PID Control: discrete PID implementation.
