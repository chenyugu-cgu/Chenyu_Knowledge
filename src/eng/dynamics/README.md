# Dynamics

Dynamics studies bodies **in motion** and the forces that cause it. Where [statics](../statics/README.md) sets the net force to zero, dynamics relates the net force to acceleration. It splits into **kinematics** (the geometry of motion, without asking why) and **kinetics** (motion linked to its causes).

## The Two Halves

- **Kinematics** — position, velocity, acceleration, and their relationships in time and space. See [Kinematics](kinematics.md).
- **Kinetics** — Newton's laws and the two great integrals of motion:
  - the **work–energy** principle (integrate force over distance), see [Work and Energy](energy.md);
  - the **impulse–momentum** principle (integrate force over time), see [Impulse and Momentum](momentum.md).

## Three Solution Methods

Most dynamics problems can be attacked three ways; choosing well saves enormous effort:

| Method | Governing relation | Best when |
|---|---|---|
| Newton–Euler | \\(\sum \mathbf{F} = m\mathbf{a}\\) | accelerations/forces at an instant |
| Work–Energy | \\(U_{1\to2} = \Delta T\\) | speeds vs. position; conservative forces |
| Impulse–Momentum | \\(\int \mathbf{F}\,dt = \Delta \mathbf{p}\\) | collisions, short impulses, time intervals |

## Chapter Map

- [Kinematics](kinematics.md)
- [Newton's Laws](newton.md)
- [Work and Energy](energy.md)
- [Impulse and Momentum](momentum.md)
- [Vibrations](vibrations.md) — the dynamics of oscillating systems.

Together with [Strength of Materials](../materials/README.md) and [Control Systems](../control/README.md), dynamics forms the analytical core of mechanical and robotic engineering.
