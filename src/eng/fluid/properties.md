# Fluid Properties

Before analyzing flow we characterize the fluid itself.

## Density and Specific Weight

\\[
\rho = \frac{m}{V}\ (\text{kg/m}^3), \qquad \gamma = \rho g\ (\text{specific weight}), \qquad SG = \frac{\rho}{\rho_{\text{water}}}.
\\]
Water is ≈1000 kg/m³, air ≈1.2 kg/m³ at sea level. Liquids are nearly **incompressible**; gases are **compressible** (density varies with pressure and temperature, \\(\rho = p/RT\\)).

## Viscosity

Viscosity is a fluid's resistance to shear. **Newton's law of viscosity** relates shear stress to the velocity gradient:
\\[
\tau = \mu\,\frac{du}{dy},
\\]
where \\(\mu\\) is the **dynamic viscosity** (Pa·s). The **kinematic viscosity** is \\(\nu = \mu/\rho\\) (m²/s).

- **Newtonian fluids** (water, air, oil): \\(\mu\\) constant.
- **Non-Newtonian fluids** (blood, paint, ketchup): \\(\mu\\) depends on shear rate — shear-thinning, shear-thickening, or yield-stress (Bingham) behavior.

## Compressibility and the Speed of Sound

The **bulk modulus** \\(K = -V\,dp/dV\\) measures resistance to volume change. The speed of sound is
\\[
a = \sqrt{\frac{K}{\rho}} = \sqrt{\gamma R T}\ (\text{ideal gas}).
\\]
Flows with \\(Ma = V/a < 0.3\\) are treated as incompressible.

## Surface Tension and Capillarity

Surface tension \\(\sigma\\) (N/m) arises from cohesive forces at an interface. It causes a pressure jump across a curved surface (Young–Laplace, \\(\Delta p = 2\sigma/r\\) for a droplet) and **capillary rise** in a tube:
\\[
h = \frac{2\sigma\cos\theta}{\rho g r}.
\\]

## Vapor Pressure and Cavitation

When local pressure drops below the **vapor pressure**, the liquid boils locally — **cavitation**. Collapsing bubbles erode pump impellers and propellers, a key design constraint in hydraulic machinery.

## See Also

- [Fluid Statics](statics.md)
- [Conservation Laws](conservation.md)
