# Models of the Node of Ranvier

The Hodgkin–Huxley model describes an unmyelinated squid axon at 6.3 °C. Stimulating human nerves needs a model of the mammalian myelinated node at 37 °C. This chapter follows the line of node models from the frog to the human, and the experimental finding that lets clinical models drop the K⁺ current entirely.

| Model | Preparation, temperature | Formulation | K⁺ current | Key point |
|---|---|---|---|---|
| Frankenhaeuser–Huxley (FH), 1964 | Frog node, 20 °C | GHK permeabilities | Yes, \\(n^2\\) | Adds a delayed non-specific current \\(i\_p\\); no temperature correction for mammals |
| CRRSS, 1987 | Rabbit node (Chiu, Ritchie, Rogart & Stagg), moved to 37 °C by Sweeney with \\(Q\_{10}\\) factors | HH-style conductances | None | Na⁺ and leak only; the standard for FES modelling |
| Schwarz–Eikhof, 1987 | Rat node, 20 and 37 °C | GHK permeabilities | Included but tiny | \\(i\_K\\) is insignificant and can be neglected |
| Schwarz, Reid & Bostock, 1995 | Human node, room temperature and 37 °C | As Schwarz–Eikhof | Fast and slow \\(i\_K\\) | \\(i\_K\\) does not shape a single AP; slow \\(i\_K\\) prevents bursting |

## Frankenhaeuser–Huxley (1964)

Frankenhaeuser and Huxley voltage-clamped the node of a frog myelinated fibre and fitted a model with two changes from HH:

1. currents are written with **GHK permeabilities** rather than linear conductances; and
2. a **delayed non-specific current** \\(i\_p\\), carried mainly by Na⁺, is added.

\\[
\dot V = \frac{-i\_{Na} - i\_K - i\_p - i\_L + i\_{st}}{C},
\\]
\\[
i\_{Na} = P\_{Na}m^2h\\,\frac{EF^2}{RT}\\,\frac{[Na]\_o - [Na]\_ie^{EF/RT}}{1 - e^{EF/RT}}, \qquad
i\_K = P\_Kn^2\\,\frac{EF^2}{RT}\\,\frac{[K]\_o - [K]\_ie^{EF/RT}}{1 - e^{EF/RT}},
\\]
\\[
i\_p = P\_pp^2\\,\frac{EF^2}{RT}\\,\frac{[Na]\_o - [Na]\_ie^{EF/RT}}{1 - e^{EF/RT}}, \qquad
i\_L = g\_L(V - V\_L),
\\]
where \\(E = V + V\_{rest}\\) is the absolute membrane potential and \\(V\\) the reduced (relative) potential. Each current has the form of the [GHK current equation](ions-membranes.md#integrating-across-the-membrane), with the permeability scaled by gating variables. Note the lower powers, \\(m^2h\\) and \\(n^2\\), instead of HH's \\(m^3h\\) and \\(n^4\\). The gates obey the same first-order kinetics as in HH, \\(\dot x = \alpha\_x(1 - x) - \beta\_xx\\).

The simulated FH currents show a large inward \\(i\_{Na}\\), outward \\(i\_L\\) and \\(i\_K\\) of comparable peak size ("equal importance"), and a small slow \\(i\_p\\). The leak is much larger than in the squid model, and it helps repolarize the node.

### Temperature correction

The FH experiments were done at 20 °C and the equations contain no temperature term. Axon-stimulation modelling began about twelve years later, and many modellers applied FH to mammalian nerve without realizing it described a frog at room temperature. The correction multiplies every rate constant by a \\(Q\_{10}\\) factor:
\\[
\alpha,\ \beta\ \longrightarrow\ \alpha,\ \beta\times Q\_{10}^{(T - 293)/10}\qquad (T\text{ in K}).
\\]

| Gate | \\(Q\_{10}\\) for \\(\alpha\\) | \\(Q\_{10}\\) for \\(\beta\\) |
|---|---|---|
| \\(m\\) | 1.8 | 1.7 |
| \\(h\\) | 2.8 | 2.9 |
| \\(n\\) | 3.2 | 2.8 |

The general idea: a rate that changes by a factor \\(Q\_{10}\\) for every 10 °C scales as \\(Q\_{10}^{\Delta T/10}\\). Going from 20 to 37 °C multiplies the \\(h\\) and \\(n\\) rates by about \\(2.8^{1.7}\approx 5.8\\), but \\(m\\) by only about \\(1.8^{1.7}\approx 2.7\\). The slow processes speed up most, so the falling phase shortens and the action potential becomes briefer. About 20% less stimulus current is needed at threshold at the higher temperature. The HH temperature factor \\(k = 3^{0.1T - 0.63} = 3^{(T - 6.3)/10}\\) is the same idea with a single \\(Q\_{10} = 3\\) referenced to 6.3 °C.

## The Mammalian Node

Voltage-clamp studies of mammalian nodes changed the picture.

- **K⁺ is even less important** for the action potential at a mammalian node than at a frog node, although K⁺ channels exist. The Na⁺ \\(m\\) gate depolarizes; Na⁺ **inactivation** (\\(h\\)) together with the **leak current** repolarizes.
- **Mammalian internodes have almost no Na⁺ channels**, so demyelination blocks conduction. Diphtheria toxin demyelinates axons, but axons can adapt as Na⁺ channels redistribute into or appear in demyelinated regions.

### Rat and human nodes

**Schwarz and Eikhof (1987)** voltage-clamped rat nodes at 20 and 37 °C using FH-style GHK permeabilities. Their model includes K⁺, but the simulated currents show \\(i\_K\\) to be negligible beside a large \\(i\_{Na}\\) and a large \\(i\_L\\).

**Schwarz, Reid and Bostock (1995)** did the same for human nodes, with separate fast and slow K⁺ currents. Neither affects a single action potential, but the slow K⁺ current is needed to prevent repetitive firing (bursting). At least five types of K⁺ channel are known in myelinated axons, some possibly in the internodes.

## The CRRSS Model

In 1987 Sweeney and colleagues took the rabbit-node model of Chiu, Ritchie, Rogart and Stagg and transformed it to 37 °C with \\(Q\_{10}\\) factors. The result, the **CRRSS model**, has only two ionic currents:
\\[
\boxed{\dot V = \frac{-g\_{Na}m^2h\\,(V - V\_{Na}) - g\_L(V - V\_L) + i\_{st}}{C}}
\\]

- **No K⁺ current.**
- **HH-style conductances** rather than FH's GHK permeabilities.
- The simulated \\(i\_{Na}\\) has a single peak.

For reference, the parameters as usually quoted from the literature (they are not in the course notes) are \\(g\_{Na} = 1445\\) mS/cm², \\(g\_L = 128\\) mS/cm², \\(C = 2.5\\) µF/cm², \\(V\_{Na} = 115\\) mV and \\(V\_L = -0.01\\) mV relative to a resting potential of −80 mV, with rate functions (ms⁻¹, \\(V\\) in mV relative to rest)
\\[
\alpha\_m = \frac{97 + 0.363V}{1 + e^{(31 - V)/5.3}}, \quad
\beta\_m = \frac{\alpha\_m}{e^{(V - 23.8)/4.17}}, \quad
\beta\_h = \frac{15.6}{1 + e^{(24 - V)/10}}, \quad
\alpha\_h = \frac{\beta\_h}{e^{(V - 5.5)/5}} .
\\]
The large conductances and fast rates reflect the small area and high channel density of the node and the 37 °C temperature.

### Why K⁺ can be ignored

The justification for dropping K⁺ is experimental: voltage clamp of rat and human nodes at 37 °C shows that \\(i\_K\\) is insignificant during a single action potential. Repolarization comes from fast Na⁺ inactivation and the large leak current, both faster at body temperature. A clinical stimulation model, which asks "does this stimulus produce an action potential?", gets the same answer with the simpler CRRSS model. The caveat is repetitive firing: slow K⁺ currents shape bursting and adaptation, and a model of those needs them.

Most functional electrical stimulation (FES) studies use CRRSS nodes connected by passive myelinated internodes, driven by the extracellular potential of an electrode, which is the "two-step" approach described in [Computational Neural Modeling](../neuro/modeling.md).

## See Also

- [Hodgkin–Huxley Kinetics and Excitation](hodgkin-huxley.md): the squid model these descend from.
- [The Cable Equation and Propagation](cable.md): how nodes are linked by internodes.
- [Computational Neural Modeling](../neuro/modeling.md): the MRG double-cable model and its successors.
