# Fluid Mechanics

Fluid mechanics studies liquids and gases at rest and in motion. It governs pipe networks, pumps and turbines, aircraft and ship design, weather, blood flow, and lubrication — anywhere a substance flows.

## What Makes Fluids Different

A fluid cannot resist shear at rest; it deforms continuously under any shear stress. This single fact distinguishes fluid mechanics from [solid mechanics](../materials/README.md) and leads to the central role of **viscosity** and **pressure**.

## The Continuum and Key Dimensionless Numbers

We treat fluids as continua and characterize flows by dimensionless groups:

| Number | Definition | Compares |
|---|---|---|
| Reynolds \\(Re\\) | \\(\rho V L/\mu\\) | inertia vs. viscous forces (laminar/turbulent) |
| Mach \\(Ma\\) | \\(V/a\\) | speed vs. sound (compressibility) |
| Froude \\(Fr\\) | \\(V/\sqrt{gL}\\) | inertia vs. gravity (free surfaces) |
| Weber \\(We\\) | \\(\rho V^2 L/\sigma\\) | inertia vs. surface tension |

The **Reynolds number** is the single most important: it predicts whether flow is smooth (laminar) or chaotic (turbulent).

## Chapter Map

- [Fluid Properties](properties.md) — density, viscosity, surface tension.
- [Fluid Statics](statics.md) — hydrostatic pressure, buoyancy, manometers.
- [Conservation Laws](conservation.md) — mass, momentum, energy; Bernoulli; Navier–Stokes.
- [Internal Flows](internal.md) — pipes, head loss, the Moody chart.
- [External Flows](external.md) — drag, lift, boundary layers.
- [Turbulence](turbulence.md)

This section connects to [Thermodynamics](../thermo/README.md) (compressible/energy) and [Conservation Laws in calculus](../../math/calculus/vector.md) (divergence, vector fields).
