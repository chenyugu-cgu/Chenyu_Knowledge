# Axial Loading

An **axially loaded** member carries force along its length, producing uniform normal stress and elongation. Bars, columns, bolts, and truss members are the prototypical cases.

## Stress and Deformation

For a prismatic bar of cross-section \\(A\\) carrying axial force \\(N\\),
\\[
\sigma = \frac{N}{A}, \qquad \delta = \frac{N L}{A E}.
\\]
The elongation \\(\delta\\) is analogous to a spring extension with stiffness \\(k = AE/L\\). For varying load or section, integrate:
\\[
\delta = \int_0^L \frac{N(x)}{A(x)E}\,dx.
\\]

## Statically Indeterminate Members

When equilibrium alone cannot find the forces (e.g. a bar fixed at both ends), add a **compatibility** condition on deformations. For a bar fixed at both ends with a load applied at an interior point, the reactions split so that the net elongation is zero:
\\[
\delta_{\text{total}} = 0 \ \Rightarrow\ \text{relation between } R_A \text{ and } R_B.
\\]

## Thermal Stress

A temperature change \\(\Delta T\\) causes free thermal strain \\(\varepsilon_T = \alpha\,\Delta T\\), where \\(\alpha\\) is the coefficient of thermal expansion. If the member is **restrained**, this strain is prevented and a stress develops:
\\[
\sigma_T = E\,\alpha\,\Delta T.
\\]
This is why bridges have expansion joints and rails can buckle in heat.

## Stress Concentrations

Geometric discontinuities (holes, fillets, notches) raise local stress above the nominal value:
\\[
\sigma_{\max} = K_t\,\sigma_{\text{nom}},
\\]
where the **stress-concentration factor** \\(K_t\\) (from charts) can exceed 3 for a circular hole. These spots are where fatigue cracks start — see [Failure Theories](failure.md).

## Worked Example: Stepped Bar

A two-segment steel bar (\\(E=200\\) GPa) carries \\(N = 50\\) kN. Segment 1: \\(A_1 = 500\\) mm², \\(L_1 = 1\\) m; segment 2: \\(A_2 = 250\\) mm², \\(L_2 = 0.5\\) m.
\\[
\sigma_1 = \frac{50{,}000}{500\times10^{-6}} = 100\ \text{MPa}, \quad \sigma_2 = 200\ \text{MPa},
\\]
\\[
\delta = \frac{N L_1}{A_1 E} + \frac{N L_2}{A_2 E} = 0.5 + 0.5 = 1.0\ \text{mm}.
\\]

## See Also

- [Stress and Strain](stress-strain.md)
- [Trusses and Frames](../statics/trusses.md)
- [Failure Theories](failure.md)
