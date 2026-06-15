# Newton's Laws

Newton's three laws connect motion to its causes and underpin all of classical kinetics.

## The Three Laws

1. **Inertia:** a body remains at rest or in uniform motion unless acted on by a net external force.
2. **Momentum:** the net force equals the rate of change of momentum,
\\[
\sum \mathbf{F} = \frac{d\mathbf{p}}{dt} = m\mathbf{a}\quad(\text{constant }m).
\\]
3. **Action–reaction:** forces occur in equal and opposite pairs acting on different bodies.

## Equations of Motion for a Particle

Resolve \\(\sum \mathbf{F} = m\mathbf{a}\\) into convenient coordinates:
\\[
\text{rectangular: } \sum F_x = m a_x,\ \sum F_y = m a_y;
\\]
\\[
\text{normal–tangential: } \sum F_t = m a_t,\ \sum F_n = m\frac{v^2}{\rho}.
\\]
The normal equation is the **centripetal** equation governing circular motion, banked curves, and orbits.

## Rigid-Body Kinetics

A rigid body obeys both a translational and a rotational equation:
\\[
\sum \mathbf{F} = m\,\mathbf{a}_G, \qquad \sum M_G = I_G \alpha,
\\]
where \\(\mathbf{a}_G\\) is the acceleration of the mass center and \\(I_G\\) the mass moment of inertia about it. The **parallel-axis theorem** shifts the inertia to another axis: \\(I = I_G + m d^2\\).

## Mass Moment of Inertia (common bodies)

| Body | Axis | \\(I\\) |
|---|---|---|
| Slender rod (length \\(L\\)) | through center | \\(\tfrac{1}{12}mL^2\\) |
| Solid disk/cylinder (radius \\(r\\)) | central | \\(\tfrac{1}{2}mr^2\\) |
| Solid sphere | central | \\(\tfrac{2}{5}mr^2\\) |
| Thin hoop | central | \\(mr^2\\) |

## Worked Example: Atwood Machine

Two masses \\(m_1 > m_2\\) hang over a massless, frictionless pulley. Writing \\(\sum F = ma\\) for each:
\\[
a = \frac{(m_1 - m_2)g}{m_1 + m_2}, \qquad T = \frac{2 m_1 m_2 g}{m_1 + m_2}.
\\]

## D'Alembert's Principle

Introducing the **inertial force** \\(-m\mathbf{a}\\) recasts kinetics as a statics problem (\\(\sum \mathbf{F} - m\mathbf{a} = 0\\)) — a "dynamic equilibrium" that is often easier to set up.

## See Also

- [Kinematics](kinematics.md)
- [Work and Energy](energy.md)
- [Impulse and Momentum](momentum.md)
