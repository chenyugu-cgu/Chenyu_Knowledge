# Entropy and Irreversibility

**Entropy** quantifies the second law: the dispersal of energy and the irreversibility of real processes. It is the property that tells us which way a process can go and how much useful work is irretrievably lost.

## Definition

For a reversible process,
\\[
dS = \frac{\delta Q_{\text{rev}}}{T}, \qquad \Delta S = \int_1^2 \frac{\delta Q_{\text{rev}}}{T}.
\\]
Entropy is a **state function**: \\(\Delta S\\) depends only on endpoints, even when computed via a reversible path replacing an irreversible one.

## The Increase-of-Entropy Principle

For any process in an isolated system,
\\[
\Delta S_{\text{universe}} = \Delta S_{\text{system}} + \Delta S_{\text{surroundings}} \ge 0,
\\]
with equality only for reversible processes. Entropy generation \\(S_{\text{gen}} > 0\\) measures irreversibility.

## Entropy of an Ideal Gas

\\[
\Delta s = c_p \ln\frac{T_2}{T_1} - R\ln\frac{p_2}{p_1} = c_v\ln\frac{T_2}{T_1} + R\ln\frac{v_2}{v_1}.
\\]
An **isentropic** (reversible adiabatic) process has \\(\Delta s = 0\\), giving \\(T v^{\gamma-1} = \text{const}\\) and \\(p v^{\gamma} = \text{const}\\).

## Statistical Interpretation

Boltzmann linked entropy to the number of microstates \\(\Omega\\):
\\[
S = k_B \ln\Omega,
\\]
so entropy measures disorder/probability. The second law is then overwhelmingly likely rather than absolute — systems evolve toward macrostates with the most microstates.

## Availability (Exergy)

The maximum useful work obtainable as a system comes to equilibrium with its environment (at \\(T_0\\)) is its **exergy**. Irreversibility destroys exergy:
\\[
W_{\text{lost}} = T_0\,S_{\text{gen}}.
\\]
This **Gouy–Stodola** relation makes the cost of irreversibility concrete — friction, unrestrained expansion, and finite-\\(\Delta T\\) heat transfer all destroy capacity to do work.

## Sources of Irreversibility

- Friction and viscous dissipation
- Heat transfer across a finite temperature difference
- Unrestrained (free) expansion
- Mixing of different substances
- Electrical resistance, hysteresis, plastic deformation

## See Also

- [Laws of Thermodynamics](laws.md)
- [Power Cycles](cycles.md)
