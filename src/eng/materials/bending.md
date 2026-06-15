# Bending and Shear

Beams carry transverse loads primarily by **bending**. Understanding bending stress and transverse shear is the heart of beam design.

## Shear and Moment Diagrams

Internal **shear force** \\(V(x)\\) and **bending moment** \\(M(x)\\) vary along the beam and are related to the distributed load \\(w(x)\\) by
\\[
\frac{dV}{dx} = -w(x), \qquad \frac{dM}{dx} = V(x).
\\]
Constructing \\(V\\) and \\(M\\) diagrams locates the maximum moment — where bending stress is worst.

## The Flexure Formula

For pure bending, plane sections remain plane, giving a linear stress distribution about the **neutral axis** (which passes through the centroid):
\\[
\sigma = -\frac{M y}{I}, \qquad \sigma_{\max} = \frac{M c}{I} = \frac{M}{S},
\\]
where \\(I\\) is the second moment of area, \\(c\\) the distance to the extreme fiber, and \\(S = I/c\\) the **section modulus**. The top and bottom fibers see the largest tension/compression; the neutral axis sees zero.

## Second Moment of Area

| Section | \\(I\\) about centroidal axis |
|---|---|
| Rectangle (\\(b \times h\\)) | \\(\dfrac{b h^3}{12}\\) |
| Circle (radius \\(r\\)) | \\(\dfrac{\pi r^4}{4}\\) |
| Hollow circle | \\(\dfrac{\pi}{4}(r_o^4 - r_i^4)\\) |

The cubic dependence on \\(h\\) is why beams are deep, and why I-beams put material far from the neutral axis.

## Transverse Shear Stress

Bending also produces shear stress across the section:
\\[
\tau = \frac{V Q}{I b},
\\]
where \\(Q\\) is the first moment of the area above the point of interest and \\(b\\) the width there. Shear stress is **maximum at the neutral axis** and zero at the top/bottom fibers — opposite to bending stress.

## Worked Example: Simply Supported Beam

A beam of span \\(L\\) with a central point load \\(P\\) has maximum moment at midspan:
\\[
M_{\max} = \frac{P L}{4}, \qquad \sigma_{\max} = \frac{M_{\max}}{S} = \frac{P L}{4 S}.
\\]
For a uniform load \\(w\\), \\(M_{\max} = wL^2/8\\).

## Composite and Unsymmetric Beams

For beams of two materials, transform sections by the modular ratio \\(n = E_1/E_2\\). For unsymmetric bending or sections without an axis of symmetry, the neutral axis tilts and the general flexure formula with products of inertia applies.

## See Also

- [Center of Gravity](../statics/center-mass.md) — locating the neutral axis.
- [Deflection of Beams](deflection.md)
- [Failure Theories](failure.md)
