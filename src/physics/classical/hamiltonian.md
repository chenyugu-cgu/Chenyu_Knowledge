# Hamiltonian Mechanics

Hamiltonian mechanics recasts dynamics in **phase space** — coordinates and momenta — giving first-order equations with deep symmetry. It is the gateway to statistical and quantum mechanics and to optimal control.

## The Hamiltonian

Define the **generalized momentum** \\(p_i = \partial L/\partial \dot{q}_i\\) and the **Hamiltonian** via a Legendre transform:
\\[
H(q, p, t) = \sum_i p_i \dot{q}_i - L.
\\]
For typical systems \\(H = T + V\\) — the total energy.

## Hamilton's Equations

The dynamics become a symmetric pair of first-order ODEs:
\\[
\dot{q}_i = \frac{\partial H}{\partial p_i}, \qquad
\dot{p}_i = -\frac{\partial H}{\partial q_i}.
\\]
The \\(2n\\)-dimensional **phase space** \\((q, p)\\) is the natural arena; trajectories never cross, and (Liouville's theorem) phase-space volume is conserved.

## Conservation Laws and Symmetry

If \\(H\\) does not depend explicitly on time, energy is conserved (\\(dH/dt = 0\\)). More generally, **Noether's theorem** ties each continuous symmetry to a conserved quantity: time-translation → energy, space-translation → momentum, rotation → angular momentum.

## Poisson Brackets

The bracket
\\[
\{f, g\} = \sum_i\left(\frac{\partial f}{\partial q_i}\frac{\partial g}{\partial p_i} - \frac{\partial f}{\partial p_i}\frac{\partial g}{\partial q_i}\right)
\\]
gives \\(\dot{f} = \{f, H\}\\) and is the classical precursor of the quantum commutator — the formal bridge to [quantum mechanics](../modern/quantum.md).

## Engineering Relevance

- **Optimal control** — Pontryagin's maximum principle introduces a control Hamiltonian and costate equations identical in form to Hamilton's. See [Optimal Control](../../eng/control/optimal.md).
- **Symplectic integrators** preserve phase-space structure for accurate long-time simulation.

## See Also

- [Lagrangian Mechanics](lagrangian.md)
- [Optimal Control](../../eng/control/optimal.md)
- [Statistical Mechanics](../modern/statistical-mechanics.md)
