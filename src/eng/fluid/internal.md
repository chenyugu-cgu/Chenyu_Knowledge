# Internal Flows

Internal flows are bounded by solid walls — flow in pipes, ducts, and channels. The key design quantities are flow rate, pressure drop, and pumping power.

## Laminar vs. Turbulent

The **Reynolds number** \\(Re = \rho V D/\mu = VD/\nu\\) classifies pipe flow:

- \\(Re < 2300\\): **laminar** — smooth, orderly, parabolic velocity profile.
- \\(2300 < Re < 4000\\): **transitional**.
- \\(Re > 4000\\): **turbulent** — chaotic, mixing, flatter profile.

## Fully Developed Laminar Flow (Hagen–Poiseuille)

For laminar flow in a circular pipe, the velocity is parabolic and the flow rate is
\\[
Q = \frac{\pi r^4 \Delta p}{8\mu L},
\\]
the **Hagen–Poiseuille law**. Note the fourth-power dependence on radius — halving a pipe's diameter cuts flow 16-fold at fixed pressure (crucial in microfluidics and blood vessels).

## Head Loss and the Darcy–Weisbach Equation

Friction causes a pressure (head) loss:
\\[
h_f = f\,\frac{L}{D}\,\frac{V^2}{2g},
\\]
where \\(f\\) is the **Darcy friction factor**. For laminar flow \\(f = 64/Re\\); for turbulent flow \\(f\\) depends on \\(Re\\) and relative roughness \\(\varepsilon/D\\) via the **Colebrook equation**, read graphically from the **Moody chart**.

## Minor Losses

Fittings, bends, valves, and area changes add losses \\(h_m = K\,\dfrac{V^2}{2g}\\), where \\(K\\) is a tabulated loss coefficient. Total loss is \\(h_L = h_f + \sum h_m\\).

## Pumping Power

The power a pump must supply to overcome losses and lift fluid is
\\[
P = \frac{\rho g Q\, h_{\text{pump}}}{\eta_{\text{pump}}}.
\\]

## Worked Example: Pipe Sizing

Water (\\(\nu = 10^{-6}\\) m²/s) at \\(V = 2\\) m/s in a \\(D = 0.05\\) m pipe gives \\(Re = 10^5\\) — turbulent. From the Moody chart (smooth pipe) \\(f \approx 0.018\\), so over \\(L = 100\\) m,
\\[
h_f = 0.018\cdot\frac{100}{0.05}\cdot\frac{2^2}{2\cdot9.81} \approx 7.3\ \text{m of head}.
\\]

## See Also

- [Conservation Laws](conservation.md)
- [Turbulence](turbulence.md)
