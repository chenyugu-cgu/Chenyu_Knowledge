# Convection

Convection transfers heat between a surface and a moving fluid. It couples [heat transfer](README.md) to [fluid mechanics](../fluid/README.md): the flow field carries the energy.

## Newton's Law of Cooling

\\[
q = h A (T_s - T_\infty),
\\]
where \\(h\\) is the **convective heat-transfer coefficient** (W/m²·K). Unlike \\(k\\), \\(h\\) is not a material property — it depends on geometry, flow, and fluid, and is the central quantity to estimate.

## Free vs. Forced Convection

- **Forced** — flow driven externally (fan, pump). Higher \\(h\\).
- **Free (natural)** — flow driven by buoyancy from the heating itself. Lower \\(h\\), governed by the Grashof/Rayleigh numbers.

## Dimensionless Correlations

\\(h\\) is found from empirical correlations among dimensionless groups:
\\[
Nu = \frac{hL}{k}, \quad Re = \frac{\rho V L}{\mu}, \quad Pr = \frac{\mu c_p}{k},
\\]
with the **Nusselt number** giving \\(h\\) once \\(Nu = f(Re, Pr)\\) is known (e.g. Dittus–Boelter for pipe flow). \\(Pr\\) compares momentum and thermal diffusion; \\(Re\\) sets laminar vs. turbulent (see [Internal Flows](../fluid/internal.md)).

## The Thermal Boundary Layer

Just as a velocity boundary layer forms on a surface (see [External Flows](../fluid/external.md)), a **thermal boundary layer** sets the temperature gradient at the wall and hence \\(h\\). Turbulent flow thins it and raises \\(h\\) — why fans and stirring cool faster.

## Boiling and Condensation

Phase-change convection achieves very high \\(h\\) by exploiting latent heat — central to power cycles, refrigeration, and heat pipes. The boiling curve shows distinct nucleate, transition, and film regimes.

## Applications

Electronics cooling, engine and turbine cooling, HVAC, heat exchangers, and bioheat transfer (blood perfusion convects heat in tissue).

## See Also

- [Conduction](conduction.md)
- [Internal Flows](../fluid/internal.md), [External Flows](../fluid/external.md)
- [Heat Exchangers](exchangers.md)
