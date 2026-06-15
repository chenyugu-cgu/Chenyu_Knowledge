# Turbulence

Turbulence is chaotic, three-dimensional, rotational fluid motion across a wide range of scales. It is ubiquitous (most engineering and natural flows are turbulent) and remains one of the great unsolved problems of classical physics.

## Characteristics

- **Irregular and chaotic** — sensitive to initial conditions, effectively unpredictable in detail.
- **Diffusive** — vastly enhances mixing of momentum, heat, and mass.
- **Rotational** — full of eddies (vortices) spanning many sizes.
- **Dissipative** — kinetic energy continuously converts to heat at the smallest scales.
- **Multi-scale** — a continuum of eddy sizes from the geometry scale down to the Kolmogorov scale.

## The Energy Cascade

Richardson's picture, made quantitative by **Kolmogorov (1941)**: energy enters at large scales, cascades to smaller eddies without loss, and dissipates at the smallest (Kolmogorov) scale \\(\eta = (\nu^3/\varepsilon)^{1/4}\\). In the inertial range the energy spectrum follows the famous **−5/3 law**:
\\[
E(k) \propto \varepsilon^{2/3} k^{-5/3}.
\\]

## Reynolds Averaging (RANS)

Decompose each quantity into a mean and fluctuation, \\(u = \bar{u} + u'\\). Averaging the Navier–Stokes equations yields the **Reynolds-averaged** equations with an extra term — the **Reynolds stress** \\(-\rho\overline{u_i' u_j'}\\) — representing turbulent momentum transport. This term must be modeled (the **closure problem**).

## Turbulence Models

| Approach | Idea | Cost |
|---|---|---|
| RANS (k–ε, k–ω) | model all turbulence via transport equations | cheap; engineering standard |
| LES | resolve large eddies, model small ones | moderate |
| DNS | resolve all scales directly | enormous; research only |

The choice trades accuracy for computational cost; RANS dominates industrial CFD.

## Engineering Consequences

- **Friction:** turbulent pipe/skin friction far exceeds laminar (the Moody chart's turbulent branch).
- **Mixing and heat transfer:** turbulence is exploited in combustors, heat exchangers, and chemical reactors.
- **Drag and noise:** turbulent boundary layers and wakes drive drag and aeroacoustic noise.

## See Also

- [External Flows](external.md)
- [Internal Flows](internal.md)
- [Partial Differential Equations](../../math/numerical/pdes.md) — the numerical machinery of CFD.
