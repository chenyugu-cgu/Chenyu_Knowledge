# Physical Chemistry

Physical chemistry applies physics — thermodynamics, kinetics, quantum theory — to chemical systems. It answers *whether* a reaction happens, *how fast*, and *how much energy* is involved.

## Thermochemistry

Reactions absorb or release energy. The enthalpy change \\(\Delta H\\) is negative for exothermic reactions. Spontaneity is set by the **Gibbs free energy**:
\\[
\Delta G = \Delta H - T\Delta S.
\\]
\\(\Delta G < 0\\) → spontaneous. This connects directly to [thermodynamics](../../eng/thermo/laws.md) and [entropy](../../eng/thermo/entropy.md), and governs whether biochemical reactions proceed.

## Chemical Equilibrium

Reversible reactions reach equilibrium where forward and reverse rates balance, characterized by
\\[
K = \prod \frac{[\text{products}]^{\nu}}{[\text{reactants}]^{\nu}}, \qquad \Delta G = \Delta G^\circ + RT\ln Q.
\\]
Le Châtelier's principle predicts how equilibrium shifts with concentration, pressure, and temperature.

## Reaction Kinetics

Rates depend on concentration and temperature:
\\[
\text{rate} = k[A]^m[B]^n, \qquad k = A\,e^{-E_a/RT}\ \text{(Arrhenius)}.
\\]
The **activation energy** \\(E_a\\) sets the temperature sensitivity; **catalysts** (including enzymes) lower it dramatically — the bridge to [biochemistry](biochemistry.md).

## Electrochemistry

Redox reactions can drive or be driven by electric current. Cell potential follows the **Nernst equation**:
\\[
E = E^\circ - \frac{RT}{nF}\ln Q.
\\]
This governs **batteries and fuel cells**, **corrosion**, electroplating, and electrochemical **biosensors** (glucose meters, pH/ion electrodes) — see [Bioinstrumentation](../../app/biomed/instrumentation.md).

## See Also

- [Laws of Thermodynamics](../../eng/thermo/laws.md)
- [Biochemistry](biochemistry.md)
- [Bioinstrumentation](../../app/biomed/instrumentation.md)
