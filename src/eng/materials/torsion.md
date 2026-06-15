# Torsion

Torsion is the twisting of a member by a moment (torque) about its axis. Drive shafts, axles, screwdrivers, and structural members under eccentric load all experience torsion.

## Circular Shafts

For a circular shaft of radius \\(r\\) carrying torque \\(T\\), the shear stress varies linearly from zero at the center to a maximum at the surface:
\\[
\tau = \frac{T \rho}{J}, \qquad \tau_{\max} = \frac{T r}{J},
\\]
where \\(\rho\\) is the radial distance and \\(J\\) is the **polar moment of inertia**:
\\[
J = \frac{\pi r^4}{2}\ (\text{solid}), \qquad J = \frac{\pi}{2}(r_o^4 - r_i^4)\ (\text{hollow}).
\\]

## Angle of Twist

The total twist over length \\(L\\) is
\\[
\phi = \frac{T L}{J G},
\\]
with \\(G\\) the shear modulus. Like axial deformation, this is a "torsional spring" with stiffness \\(k_t = JG/L\\). For varying torque, \\(\phi = \int_0^L \frac{T(x)}{J(x)G}\,dx\\).

## Power Transmission

A rotating shaft transmits power
\\[
P = T\,\omega,
\\]
where \\(\omega\\) is angular speed (rad/s). Shaft design for machinery starts from required power and speed: \\(T = P/\omega\\), then size \\(r\\) so \\(\tau_{\max}\\) stays below the allowable shear stress.

## Why Hollow Shafts Win

Because material near the axis carries little stress, removing it barely reduces \\(J\\) while greatly reducing weight. A hollow shaft has a far higher strength-to-weight ratio than a solid one of equal mass — which is why drive shafts and bicycle frames are tubes.

## Non-Circular Sections

Non-circular cross-sections **warp** (cross-sections don't stay plane), so the simple formula fails. Thin-walled closed tubes use the **shear-flow** relation \\(q = \tau t = T/(2A_m)\\), where \\(A_m\\) is the area enclosed by the wall midline.

## Worked Example: Shaft Design

A shaft transmits \\(P = 100\\) kW at \\(N = 1500\\) rpm. The torque is
\\[
\omega = \frac{2\pi N}{60} = 157\ \text{rad/s}, \qquad T = \frac{P}{\omega} = 637\ \text{N·m}.
\\]
For allowable \\(\tau = 60\\) MPa, a solid shaft needs \\(r = \left(\dfrac{2T}{\pi\tau}\right)^{1/3} \approx 20\\) mm.

## See Also

- [Elasticity](elasticity.md)
- [Power Transmission in Robot Dynamics](../../app/robotics/dynamics.md)
