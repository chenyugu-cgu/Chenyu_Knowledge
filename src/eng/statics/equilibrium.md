# Forces and Equilibrium

## Forces, Moments, and Couples

A **force** is a vector \\(\mathbf{F}\\) with magnitude, direction, and point of application. The **moment** of a force about a point \\(O\\) measures its tendency to rotate the body:
\\[
\mathbf{M}_O = \mathbf{r} \times \mathbf{F}, \qquad |\mathbf{M}_O| = F\,d,
\\]
where \\(\mathbf{r}\\) is the position vector from \\(O\\) to any point on the line of action and \\(d\\) is the perpendicular (moment) arm. A **couple** is a pair of equal, opposite, non-collinear forces; it produces a pure moment \\(M = F d\\) independent of reference point.

## Equilibrium Equations

A body is in equilibrium when both the resultant force and resultant moment vanish. In 2-D:
\\[
\sum F_x = 0, \qquad \sum F_y = 0, \qquad \sum M_O = 0.
\\]
In 3-D, add \\(\sum F_z = 0\\) and moments about all three axes — six equations total.

## Free-Body Diagrams

A **free-body diagram (FBD)** isolates the body and replaces every contact and support with the force/moment it exerts. Common 2-D supports:

| Support | Reactions |
|---|---|
| Roller / smooth surface | 1 force ⟂ to surface |
| Pin / hinge | 2 force components |
| Fixed (cantilever) | 2 forces + 1 moment |
| Cable | 1 tension along the cable |

## Worked Example: Simply Supported Beam

A beam of length \\(L\\) rests on a pin at \\(A\\) and a roller at \\(B\\), carrying a point load \\(P\\) a distance \\(a\\) from \\(A\\). Taking moments about \\(A\\):
\\[
\sum M_A = 0:\quad R_B L - P a = 0 \ \Rightarrow\ R_B = \frac{P a}{L}.
\\]
Then \\(\sum F_y = 0\\) gives \\(R_A = P - R_B = P\dfrac{L-a}{L}\\). Choosing \\(A\\) as the moment center eliminated \\(R_A\\) from the first equation — the key trick.

## Distributed Loads

A distributed load \\(w(x)\\) (force per length) is replaced by an equivalent point force equal to the **area under the load curve**, acting through its **centroid**:
\\[
F_{eq} = \int_0^L w(x)\,dx, \qquad \bar{x} = \frac{\int_0^L x\,w(x)\,dx}{\int_0^L w(x)\,dx}.
\\]
A uniform load \\(w_0\\) over length \\(L\\) becomes \\(w_0 L\\) at the midpoint; a triangular load \\(w_0\\) (peak) becomes \\(\tfrac12 w_0 L\\) at \\(\tfrac{2}{3}L\\) from the zero end.

## Two- and Three-Force Members

- A **two-force member** (loaded only at two points, no weight) carries force directed along the line joining those points — pure tension or compression. This is the basis of truss analysis.
- A **three-force member** is in equilibrium only if the three forces are **concurrent** (or all parallel).

## See Also

- [Trusses and Frames](trusses.md)
- [Center of Gravity](center-mass.md)
- [Statics and Dynamics Recipes](../../cookbook/examples/mechanics.md)
