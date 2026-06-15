# Semiconductors

Semiconductors (silicon, germanium, GaAs) have conductivity between conductors and insulators, tunable by **doping**. They are the basis of every modern electronic device.

## Doping and Carriers

Pure (intrinsic) silicon has few free carriers. Adding impurities creates:
- **n-type** — donor atoms (P, As) contribute free electrons.
- **p-type** — acceptor atoms (B) create holes.

Conduction is by both electrons and holes; their concentrations satisfy the mass-action law \\(n p = n_i^2\\).

## The p–n Junction Diode

Joining p- and n-type material forms a junction that conducts in one direction. The current follows the **Shockley diode equation**:
\\[
I = I_S\left(e^{V/(n V_T)} - 1\right), \qquad V_T = \frac{kT}{q} \approx 26\ \text{mV at room temp}.
\\]
Diodes rectify AC to DC, clip and clamp signals, and (as LEDs and photodiodes) convert between light and current.

## Transistors

The **bipolar junction transistor (BJT)** amplifies: a small base current controls a large collector current, \\(I_C = \beta I_B\\). The **MOSFET** uses a gate voltage to control a channel; in saturation,
\\[
I_D = \tfrac{1}{2}\mu C_{ox}\frac{W}{L}(V_{GS} - V_{th})^2.
\\]
MOSFETs switch and amplify with near-zero gate current and dominate digital ICs (CMOS).

## Operational Amplifiers

The op-amp is a high-gain differential amplifier. With negative feedback, the two **golden rules** (infinite input impedance, virtual short between inputs) make analysis trivial:

| Configuration | Gain |
|---|---|
| Inverting | \\(-R_f/R_{in}\\) |
| Non-inverting | \\(1 + R_f/R_{in}\\) |
| Integrator | \\(-\dfrac{1}{RC}\int v\,dt\\) |
| Differentiator | \\(-RC\,\dfrac{dv}{dt}\\) |

Op-amps build amplifiers, filters, comparators, and the analog front-ends of sensors.

## Power and Switching Devices

MOSFETs, IGBTs, and thyristors switch large currents in power electronics — converters, inverters, and motor drives — enabling everything from EV traction to grid-scale renewables.

## See Also

- [Circuit Laws](circuits.md)
- [Digital Logic](digital.md)
- [Crystal Structures](../../app/materials-science/crystals.md)
