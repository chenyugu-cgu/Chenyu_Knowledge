# Heat Exchangers

A **heat exchanger** transfers heat between two fluids without mixing them — radiators, condensers, boilers, HVAC coils, and the oxygenators and dialyzers of medical devices.

## Configurations

- **Parallel flow** — both fluids enter the same end.
- **Counterflow** — fluids flow in opposite directions; the most thermodynamically efficient (largest mean \\(\Delta T\\)).
- **Crossflow** — fluids cross at right angles (car radiators).
- **Shell-and-tube** — the industrial workhorse.

## The Overall Heat-Transfer Coefficient

Combining convection on each side and conduction through the wall as resistances in series:
\\[
\frac{1}{UA} = \frac{1}{h_i A_i} + R_{\text{wall}} + \frac{1}{h_o A_o}.
\\]
Fouling (deposits) adds resistance over time and must be allowed for in design.

## LMTD Method

For known inlet/outlet temperatures, the heat rate is
\\[
q = U A\,\Delta T_{\text{lm}}, \qquad
\Delta T_{\text{lm}} = \frac{\Delta T_1 - \Delta T_2}{\ln(\Delta T_1/\Delta T_2)},
\\]
the **log-mean temperature difference** — it correctly averages the varying \\(\Delta T\\) along the exchanger.

## The ε–NTU Method

When outlet temperatures are unknown, use **effectiveness–NTU**:
\\[
\varepsilon = \frac{q}{q_{\max}}, \qquad NTU = \frac{UA}{C_{\min}},
\\]
where \\(\varepsilon\\) is the fraction of the maximum possible heat transferred. Charts/relations give \\(\varepsilon(NTU, C_{\min}/C_{\max})\\) per configuration.

## Biomedical Examples

- **Blood oxygenators** (heart-lung machines) exchange O₂/CO₂ across membranes.
- **Hemodialyzers** exchange solutes between blood and dialysate.
- **Therapeutic hypothermia** systems control patient temperature.

These obey the same transport principles as industrial exchangers, with biocompatibility added.

## See Also

- [Convection](convection.md)
- [Conservation Laws](../fluid/conservation.md)
- [Bioinstrumentation](../../app/biomed/instrumentation.md)
