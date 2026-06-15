# Center of Gravity

The **center of gravity** is the point through which the resultant weight of a body acts. For a uniform gravitational field it coincides with the **center of mass**, and for a homogeneous body it coincides with the **centroid** of its geometry. Locating it is essential for stability, balancing, and computing moments of distributed loads.

## Definitions

For a body with density \\(\rho\\),
\\[
\bar{x} = \frac{\int x\,dm}{\int dm}, \quad
\bar{y} = \frac{\int y\,dm}{\int dm}, \quad
\bar{z} = \frac{\int z\,dm}{\int dm}, \qquad dm = \rho\,dV.
\\]
For a homogeneous body \\(\rho\\) cancels and the integrals reduce to the **centroid** of the volume (or area, or line).

## Centroids of Areas

For a planar area \\(A\\),
\\[
\bar{x} = \frac{1}{A}\int x\,dA, \qquad \bar{y} = \frac{1}{A}\int y\,dA.
\\]

Common results:

| Shape | \\(\bar{x}\\), \\(\bar{y}\\) from reference |
|---|---|
| Rectangle (\\(b\times h\\)) | center \\((b/2,\,h/2)\\) |
| Triangle (base \\(b\\), height \\(h\\)) | \\(h/3\\) above the base |
| Semicircle (radius \\(r\\)) | \\(4r/3\pi\\) from the flat edge |
| Quarter circle | \\(4r/3\pi\\) along each axis |

## Composite Bodies

Most real shapes are sums (and holes are subtractions) of simple shapes. Use the weighted average
\\[
\bar{x} = \frac{\sum A_i \bar{x}_i}{\sum A_i}, \qquad \bar{y} = \frac{\sum A_i \bar{y}_i}{\sum A_i},
\\]
treating cut-outs as **negative** areas. The same formula with \\(A\to V\\) or \\(A\to m\\) handles volumes and masses.

### Worked Example

An L-shaped area is split into two rectangles, \\(A_1 = 20\\) at \\(\bar{x}_1 = 1\\) and \\(A_2 = 12\\) at \\(\bar{x}_2 = 5\\):
\\[
\bar{x} = \frac{20(1) + 12(5)}{20 + 12} = \frac{80}{32} = 2.5.
\\]

## Pappus–Guldinus Theorems

Surfaces and volumes of revolution come for free from the centroid of the generating curve/area:
\\[
A = 2\pi \bar{r} L, \qquad V = 2\pi \bar{r} A,
\\]
where \\(\bar{r}\\) is the centroidal distance to the axis, \\(L\\) the generating arc length, and \\(A\\) the generating area.

## Stability

A body resting on a base is stable as long as the vertical line through its center of gravity falls **within the support base**. The lower the center of gravity and the wider the base, the more stable the body — the principle behind race-car design and crane counterweights.

## See Also

- [Forces and Equilibrium](equilibrium.md) — distributed-load resultants act at the centroid.
- [Bending and Shear](../materials/bending.md) — the centroid is the neutral axis in bending.
