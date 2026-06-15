# Heat Transfer

Heat transfer is the science of thermal energy in motion. Where [thermodynamics](../thermo/README.md) tells you *how much* energy moves between equilibrium states, heat transfer tells you *how fast* and *by what path*. It is essential to engine cooling, electronics thermal management, HVAC, and physiological temperature regulation.

## The Three Modes

| Mode | Mechanism | Rate law |
|---|---|---|
| **Conduction** | diffusion through matter | \\(q = -kA\,dT/dx\\) (Fourier) |
| **Convection** | fluid carrying heat | \\(q = hA(T_s - T_\infty)\\) (Newton) |
| **Radiation** | electromagnetic emission | \\(q = \varepsilon\sigma A T^4\\) (Stefan–Boltzmann) |

Real problems combine all three; the art is identifying which dominates.

## The Thermal-Circuit Analogy

Heat flow is analogous to current, temperature difference to voltage, and **thermal resistance** to electrical resistance:
\\[
q = \frac{\Delta T}{R_{\text{th}}}, \qquad R_{\text{cond}} = \frac{L}{kA}, \quad R_{\text{conv}} = \frac{1}{hA}.
\\]
Series and parallel resistances combine just like [circuits](../electrical/circuits.md), making multilayer walls and finned surfaces easy to analyze.

## Chapter Map

- [Conduction](conduction.md)
- [Convection](convection.md)
- [Radiation](radiation.md)
- [Heat Exchangers](exchangers.md)

## Connections

Heat transfer couples to [Fluid Mechanics](../fluid/README.md) (convection), [PDEs](../../math/diffeq/pdes.md) (the heat equation), and [biomedical](../../app/biomed/README.md) thermal therapies and bioheat modeling.
