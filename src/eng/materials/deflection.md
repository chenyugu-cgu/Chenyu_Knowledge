# Deflection of Beams

Even when a beam is strong enough, it must also be **stiff** enough — floors must not bounce, shafts must not sag into their bearings. Deflection analysis predicts how much a beam bends.

## The Elastic Curve

The deflection \\(v(x)\\) of a beam is governed by the moment–curvature relation:
\\[
EI\,\frac{d^2 v}{dx^2} = M(x).
\\]
Integrating once gives the **slope** \\(\theta = dv/dx\\); integrating twice gives the **deflection** \\(v\\). The two constants of integration are fixed by **boundary conditions** (zero deflection at supports, zero slope at a fixed end).

## Higher-Order Form

Differentiating and using \\(dM/dx = V\\) and \\(dV/dx = -w\\):
\\[
EI\,\frac{d^4 v}{dx^4} = -w(x),
\\]
which can be integrated directly from the load.

## Standard Results

| Beam & load | Max deflection |
|---|---|
| Cantilever, end load \\(P\\) | \\(\dfrac{P L^3}{3EI}\\) |
| Cantilever, UDL \\(w\\) | \\(\dfrac{w L^4}{8EI}\\) |
| Simply supported, central \\(P\\) | \\(\dfrac{P L^3}{48EI}\\) |
| Simply supported, UDL \\(w\\) | \\(\dfrac{5 w L^4}{384 EI}\\) |

Note the strong dependence on span (\\(L^3\\) or \\(L^4\\)) and the inverse dependence on \\(EI\\) — doubling depth (which roughly increases \\(I\\) by 8) dramatically stiffens a beam.

## Methods

- **Direct integration** of \\(EIv'' = M(x)\\): general but tedious.
- **Superposition:** add standard-case deflections for combined loads (linear elasticity makes this valid).
- **Moment-area method:** use the area and centroid of the \\(M/EI\\) diagram to get slopes and deflections geometrically.
- **Castigliano's theorem:** deflection at a load = \\(\partial U/\partial P\\), where \\(U\\) is strain energy — powerful for frames and curved members.

## Worked Example: Cantilever Tip Deflection

A steel cantilever (\\(E=200\\) GPa, \\(I = 8\times10^{6}\\) mm⁴, \\(L=2\\) m) with a 5 kN end load:
\\[
v_{\max} = \frac{P L^3}{3EI} = \frac{5000\,(2)^3}{3(200\times10^9)(8\times10^{-6})} = 8.3\ \text{mm}.
\\]

## Statically Indeterminate Beams

Beams with redundant supports (propped cantilever, fixed–fixed) need compatibility conditions in addition to equilibrium — superposition with the standard deflection results is the usual route.

## See Also

- [Bending and Shear](bending.md)
- [Elasticity](elasticity.md) — strain energy for Castigliano's method.
