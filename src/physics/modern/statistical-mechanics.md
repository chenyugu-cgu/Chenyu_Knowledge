# Statistical Mechanics

Statistical mechanics derives the macroscopic laws of [thermodynamics](../../eng/thermo/README.md) from the statistics of enormous numbers of microscopic particles. It explains *why* entropy increases and temperature means what it does.

## Microstates and Macrostates

A **macrostate** (specified by \\(T, P, V\\)) corresponds to vast numbers of **microstates** (specific particle configurations). Boltzmann's insight links entropy to the count of microstates \\(\Omega\\):
\\[
S = k_B\ln\Omega.
\\]
The second law is then statistical: systems evolve toward macrostates with overwhelmingly more microstates.

## The Boltzmann Distribution

In thermal equilibrium at temperature \\(T\\), the probability of a state with energy \\(E_i\\) is
\\[
P_i = \frac{e^{-E_i/k_B T}}{Z}, \qquad Z = \sum_i e^{-E_i/k_B T},
\\]
where \\(Z\\) is the **partition function** — the master quantity from which all thermodynamic properties follow.

## From Partition Function to Thermodynamics

\\[
\langle E\rangle = -\frac{\partial \ln Z}{\partial \beta}, \qquad F = -k_B T\ln Z, \qquad S = -\frac{\partial F}{\partial T}.
\\]
This machinery recovers heat capacities, equations of state, and phase transitions from first principles.

## Quantum Statistics

Indistinguishable particles obey:
- **Fermi–Dirac** (fermions, e.g. electrons) — Pauli exclusion; governs electrons in metals and semiconductors.
- **Bose–Einstein** (bosons, e.g. photons) — enables lasers and superfluidity.

Fermi–Dirac statistics underlie [solid-state physics](solid-state.md) and the electronic properties of materials.

## Connections

Grounds [entropy](../../eng/thermo/entropy.md), informs [information theory](../../cs/information-theory/entropy.md) (Shannon entropy mirrors Boltzmann's), and underlies diffusion, noise, and fluctuation phenomena.

## See Also

- [Entropy and Irreversibility](../../eng/thermo/entropy.md)
- [Entropy and Information](../../cs/information-theory/entropy.md)
- [Distributions](../../math/probability/distributions.md)
