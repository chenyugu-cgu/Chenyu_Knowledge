# Electrical and Electronics

Electrical engineering deals with the behavior of charge, current, and electromagnetic fields, and with the devices and circuits that exploit them — from power grids to microprocessors.

## Fundamental Quantities

| Quantity | Symbol | Unit |
|---|---|---|
| Charge | \\(q\\) | coulomb (C) |
| Current | \\(i = dq/dt\\) | ampere (A) |
| Voltage | \\(v\\) | volt (V) |
| Power | \\(p = vi\\) | watt (W) |
| Resistance | \\(R\\) | ohm (Ω) |
| Capacitance | \\(C\\) | farad (F) |
| Inductance | \\(L\\) | henry (H) |

## The Three Passive Elements

\\[
v_R = R i, \qquad i_C = C\frac{dv}{dt}, \qquad v_L = L\frac{di}{dt}.
\\]
Resistors dissipate energy; capacitors store it in an electric field; inductors store it in a magnetic field. These constitutive laws, plus Kirchhoff's laws, generate every linear circuit's equations.

## Chapter Map

- [Circuit Laws](circuits.md) — Ohm, Kirchhoff, network theorems.
- [AC and DC Analysis](ac-dc.md) — phasors, impedance, power.
- [Semiconductors](semiconductors.md) — diodes, transistors, op-amps.
- [Digital Logic](digital.md) — gates, Boolean algebra, sequential circuits.
- [Signal Processing](signal-processing.md) — filters, ADC/DAC, DSP.

This section is deeply tied to [Signals and Systems](../../signals/fundamentals.md): circuits are LTI systems, and their analysis uses the same Laplace/Fourier machinery.
