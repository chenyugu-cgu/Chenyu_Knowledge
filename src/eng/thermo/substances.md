# Pure Substances

A **pure substance** has a fixed chemical composition throughout (water, nitrogen, refrigerant R-134a). Its state is fixed by any two independent intensive properties, and its behavior is captured by property relations and tables.

## Phases and Phase Change

A substance exists as solid, liquid, or vapor, and transitions between them at characteristic conditions. On a \\(T\text{–}v\\) or \\(p\text{–}v\\) diagram, the **saturation dome** separates:

- **Compressed (subcooled) liquid** — left of the dome.
- **Saturated mixture** — inside the dome, liquid and vapor coexist at the saturation temperature/pressure.
- **Superheated vapor** — right of the dome.

The **quality** \\(x\\) gives the vapor mass fraction in a mixture:
\\[
x = \frac{m_{\text{vapor}}}{m_{\text{total}}}, \qquad
v = v_f + x(v_g - v_f),
\\]
and similarly for \\(u, h, s\\) between saturated-liquid (\\(f\\)) and saturated-vapor (\\(g\\)) values from steam/refrigerant tables.

## The Ideal Gas Law

At low density, gases obey
\\[
pV = nRT = mR_{\text{specific}}T,
\\]
where \\(R = 8.314\ \text{J/mol·K}\\) and \\(R_{\text{specific}} = R/M\\). The ideal-gas model is excellent for air at ordinary conditions but fails near the saturation dome and the critical point.

## Specific Heats

\\[
c_v = \left(\frac{\partial u}{\partial T}\right)_v, \qquad
c_p = \left(\frac{\partial h}{\partial T}\right)_p, \qquad
c_p - c_v = R \ (\text{ideal gas}).
\\]
The ratio \\(\gamma = c_p/c_v\\) (1.4 for air) governs adiabatic processes \\(pV^\gamma = \text{const}\\) and the speed of sound.

## Real-Gas Equations of State

When the ideal-gas law is inadequate, use the **compressibility factor** \\(Z = pv/RT\\) (from generalized charts) or cubic equations of state such as **van der Waals**:
\\[
\left(p + \frac{a}{v^2}\right)(v - b) = RT.
\\]

## Enthalpy

The combination \\(H = U + pV\\) appears whenever flow work matters (open systems, throttling, heat exchangers). For constant-pressure heating, \\(Q = \Delta H\\).

## See Also

- [Laws of Thermodynamics](laws.md)
- [Power Cycles](cycles.md)
- [Crystal Structures](../../app/materials-science/crystals.md)
