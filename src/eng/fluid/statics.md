# Fluid Statics

Fluid statics treats fluids **at rest**, where there is no shear and pressure is the only stress. It explains dams, manometers, buoyancy, and hydraulic systems.

## The Hydrostatic Equation

In a fluid at rest, pressure increases with depth:
\\[
\frac{dp}{dz} = -\rho g \ \Rightarrow\ p = p_0 + \rho g h,
\\]
where \\(h\\) is depth below the surface. Pressure is **isotropic** (the same in all directions at a point — Pascal's law) and depends only on depth, not on container shape (the hydrostatic paradox).

## Pressure Measurement

- **Absolute vs. gauge:** \\(p_{\text{abs}} = p_{\text{gauge}} + p_{\text{atm}}\\).
- **Manometers** use \\(p = \rho g h\\) across fluid columns to measure pressure differences.
- **Barometers** measure atmospheric pressure via a mercury column.

## Forces on Submerged Surfaces

The resultant hydrostatic force on a plane surface acts at the **center of pressure** (below the centroid):
\\[
F_R = \rho g \bar{h}\,A, \qquad y_{cp} = \bar{y} + \frac{I_{\bar{x}}}{\bar{y}A},
\\]
where \\(\bar{h}\\) is the centroid depth and \\(I_{\bar{x}}\\) the second moment of area. This sizes dam walls, gates, and tank walls.

## Buoyancy (Archimedes' Principle)

A submerged or floating body experiences an upward buoyant force equal to the weight of fluid displaced:
\\[
F_B = \rho_{\text{fluid}}\, g\, V_{\text{displaced}}.
\\]
A body floats when its average density is below the fluid's; the submerged fraction equals the density ratio.

## Stability of Floating Bodies

Floating stability depends on the **metacenter** \\(M\\): if it lies above the center of gravity \\(G\\), a tilt produces a restoring moment (stable). The metacentric height \\(\overline{GM}\\) is the key ship-design parameter.

## Worked Example: Iceberg

With \\(\rho_{\text{ice}} = 917\\) and \\(\rho_{\text{sea}} = 1025\\) kg/m³, the submerged fraction is \\(917/1025 \approx 0.89\\) — about 89% of an iceberg lies underwater.

## See Also

- [Fluid Properties](properties.md)
- [Center of Gravity](../statics/center-mass.md)
- [Conservation Laws](conservation.md)
