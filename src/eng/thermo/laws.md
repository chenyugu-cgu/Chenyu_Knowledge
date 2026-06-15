# Laws of Thermodynamics

## Zeroth Law

If two systems are each in thermal equilibrium with a third, they are in equilibrium with each other. This transitivity is what makes **temperature** a meaningful, measurable property and underlies all thermometry.

## First Law: Conservation of Energy

Energy is neither created nor destroyed, only converted. For a closed system,
\\[
\Delta U = Q - W,
\\]
where \\(Q\\) is heat added **to** the system and \\(W\\) is work done **by** it. In differential form \\(dU = \delta Q - \delta W\\), with \\(\delta W = p\,dV\\) for quasi-static boundary work.

For an **open system** (control volume), the steady-flow energy equation adds flow enthalpy, kinetic, and potential terms:
\\[
\dot{Q} - \dot{W}_s = \dot{m}\left[(h_2 - h_1) + \frac{V_2^2 - V_1^2}{2} + g(z_2 - z_1)\right].
\\]

## Second Law

Heat does not spontaneously flow from cold to hot; no cyclic engine can convert heat **entirely** into work. Quantitatively, the entropy of an isolated system cannot decrease:
\\[
dS \ge \frac{\delta Q}{T}, \qquad \Delta S_{\text{universe}} \ge 0,
\\]
with equality only for reversible processes. The second law sets the **maximum efficiency** of any heat engine — see [Power Cycles](cycles.md) and [Entropy](entropy.md).

## Third Law

As temperature approaches absolute zero, the entropy of a perfect crystal approaches zero:
\\[
\lim_{T\to 0} S = 0.
\\]
This provides an absolute reference for entropy and implies that absolute zero cannot be reached in finite steps.

## Heat and Work as Path Functions

\\(Q\\) and \\(W\\) depend on the **path** between states (they are inexact differentials \\(\delta Q, \delta W\\)), whereas \\(U, H, S\\) are **state functions** (exact differentials). This distinction is central: you cannot speak of the "heat content" of a state, only the heat transferred during a process.

## Worked Example: Isothermal Ideal-Gas Expansion

For an ideal gas expanding isothermally from \\(V_1\\) to \\(V_2\\), \\(\Delta U = 0\\), so all heat becomes work:
\\[
W = Q = nRT\ln\frac{V_2}{V_1}.
\\]

## See Also

- [Pure Substances](substances.md)
- [Entropy and Irreversibility](entropy.md)
