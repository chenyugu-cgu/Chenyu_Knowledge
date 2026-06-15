# Power Cycles

A **thermodynamic cycle** returns a working fluid to its initial state while continuously converting heat to work (engines) or moving heat with work (refrigerators). Cycles are analyzed on \\(p\text{–}v\\) and \\(T\text{–}s\\) diagrams, where enclosed area equals net work or heat.

## The Carnot Cycle (the limit)

The reversible Carnot cycle — two isothermal and two adiabatic processes — sets the maximum possible efficiency between hot reservoir \\(T_H\\) and cold reservoir \\(T_C\\):
\\[
\eta_{\text{Carnot}} = 1 - \frac{T_C}{T_H}.
\\]
No real engine can exceed this; it depends only on the reservoir temperatures.

## Rankine Cycle (steam power plants)

The vapor power cycle: pump → boiler → turbine → condenser.
\\[
\eta = \frac{w_{\text{turbine}} - w_{\text{pump}}}{q_{\text{boiler}}} \approx \frac{(h_3 - h_4) - (h_2 - h_1)}{h_3 - h_2}.
\\]
Efficiency improves with **superheating**, **reheat**, and **regeneration** (feedwater heating). It powers most of the world's electricity (coal, nuclear, solar-thermal).

## Otto Cycle (gasoline engines)

Idealized spark-ignition engine with isentropic compression/expansion and constant-volume heat addition. Efficiency depends only on compression ratio \\(r\\):
\\[
\eta_{\text{Otto}} = 1 - \frac{1}{r^{\gamma - 1}}.
\\]
Higher compression → higher efficiency, limited by knock.

## Diesel Cycle

Compression-ignition engine; heat added at constant pressure. Efficiency is slightly below an Otto cycle of equal compression ratio but Diesels run at much higher \\(r\\).

## Brayton Cycle (gas turbines / jet engines)

Compressor → combustor → turbine, all at steady flow. Efficiency rises with pressure ratio \\(r_p\\):
\\[
\eta_{\text{Brayton}} = 1 - \frac{1}{r_p^{(\gamma-1)/\gamma}}.
\\]

## Refrigeration and Heat Pumps

Running a cycle in reverse moves heat from cold to hot using work. Performance is the **coefficient of performance**:
\\[
\text{COP}_{\text{ref}} = \frac{Q_C}{W}, \qquad \text{COP}_{\text{hp}} = \frac{Q_H}{W} = \text{COP}_{\text{ref}} + 1.
\\]
COP can exceed 1 — heat pumps deliver more heat than the work input because they pump existing heat.

## See Also

- [Laws of Thermodynamics](laws.md)
- [Entropy and Irreversibility](entropy.md)
