# Multivariable Calculus

Multivariable calculus is the natural extension of single-variable calculus to functions of several variables. While single-variable calculus deals with functions \\\(f(x)\\\) where \\\(x\\\) is a real number, multivariable calculus studies functions such as \\\(f(x,y)\\\) or \\\(f(x,y,z)\\\) where the input is a vector in higher-dimensional space. This extension allows us to analyze and understand phenomena that depend on multiple parameters simultaneously.

## Functions of Several Variables

A function of two variables is typically written as \\\(f(x,y)\\\), where \\\(x\\\) and \\\(y\\\) are independent variables. Similarly, a function of three variables is \\\(f(x,y,z)\\\). These functions map points in \\\(\mathbb{R}^2\\\) or \\\(\mathbb{R}^3\\\) to real numbers:

\\[
f: \mathbb{R}^2 \to \mathbb{R}, \quad (x,y) \mapsto f(x,y)
\\]

\\[
f: \mathbb{R}^3 \to \mathbb{R}, \quad (x,y,z) \mapsto f(x,y,z)
\\]

Such functions can represent surfaces, scalar fields, or physical quantities varying in space. **Level curves** (for functions of two variables) are the sets of points where the function takes on a constant value, i.e., the set \\\(\{(x, y) \mid f(x, y) = c\}\\\) for some constant \\\(c\\\). These curves can be visualized as "contour lines" on a map, showing where the function is constant. For functions of three variables, **level surfaces** are the sets \\\(\{(x, y, z) \mid f(x, y, z) = c\}\\\), representing surfaces in three-dimensional space where the function has the same value. Level curves and surfaces play a key role in visualizing and analyzing multivariable functions.

## Limits and Continuity in Higher Dimensions

The concept of limits and continuity extends naturally to functions of several variables. The limit of \\\(f(x,y)\\\) as \\\((x,y) \to (a,b)\\\) is \\\(L\\\) if for every \\\(\varepsilon > 0\\\), there exists \\\(\delta > 0\\\) such that

\\[
\sqrt{(x - a)^2 + (y - b)^2} < \delta \implies |f(x,y) - L| < \varepsilon.
\\]

Continuity at a point means the function's value matches the limit at that point.

**Path Dependence:** In multiple dimensions, a limit exists at a point only if the value approached along every possible path to that point is the same. If the limit depends on the path, the limit does not exist. This makes proving limits more subtle than in one variable.

**Differentiability:** For a function to be differentiable at a point, it must be continuous there, and the function must be well-approximated by a linear function in all directions near the point. Differentiability implies continuity, but the converse is not always true. Sufficient conditions for differentiability include the existence and continuity of all partial derivatives in a neighborhood of the point.

## Partial Derivatives

Partial derivatives measure the rate of change of a function with respect to one variable while holding others constant. For \\\(f(x,y)\\\), the partial derivatives are

\\[
\frac{\partial f}{\partial x} = \lim_{h \to 0} \frac{f(x+h,y) - f(x,y)}{h}, \quad \frac{\partial f}{\partial y} = \lim_{h \to 0} \frac{f(x,y+h) - f(x,y)}{h}.
\\]

**Mixed partial derivatives** are derivatives taken with respect to multiple variables in succession, for example, \\\(\frac{\partial^2 f}{\partial x \partial y}\\\). Under suitable conditions (such as continuity of the mixed partials near a point), **Clairaut's theorem** (also called Schwarz's theorem) states that the order of differentiation does not matter:

\\[
\frac{\partial^2 f}{\partial x \partial y} = \frac{\partial^2 f}{\partial y \partial x}
\\]

This property is fundamental in many theoretical and practical applications.

## Gradient Vector

The **gradient vector** \\\(\nabla f\\\) collects all first partial derivatives of a scalar function:

\\[
\nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right)
\\]

in two dimensions, or

\\[
\nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z} \right)
\\]

in three dimensions.

The gradient has important interpretations:
- **Directional Meaning:** The gradient at a point points in the direction of the steepest increase of the function. Its magnitude gives the rate of increase in that direction.
- **Orthogonality:** The gradient is perpendicular (normal) to the level curve (in 2D) or level surface (in 3D) passing through the point.
- **Optimization Role:** In optimization, the gradient is used to find local maxima and minima; critical points occur where the gradient is zero. Methods such as gradient ascent/descent use the gradient to iteratively find extrema.

## Directional Derivatives

The **directional derivative** generalizes the concept of derivative to any direction \\\(\mathbf{u}\\\), a unit vector. The directional derivative of \\\(f\\\) at point \\\(\mathbf{a}\\\) in the direction \\\(\mathbf{u}\\\) is

\\[
D_{\mathbf{u}} f(\mathbf{a}) = \nabla f(\mathbf{a}) \cdot \mathbf{u}.
\\]

It measures the rate of change of \\\(f\\\) moving from \\\(\mathbf{a}\\\) in the direction \\\(\mathbf{u}\\\). Geometrically, this is the slope of the surface defined by \\\(f\\\) at \\\(\mathbf{a}\\\) as you move in the direction of \\\(\mathbf{u}\\\). The maximum value of the directional derivative at a point is the magnitude of the gradient, and occurs in the direction of the gradient.

## Multiple Integrals

Multivariable calculus introduces **double** and **triple integrals** to compute volumes, masses, and other quantities over regions in higher dimensions.

- **Double integrals:** For a function \\\(f(x,y)\\\) over region \\\(R\\\),

\\[
\iint_R f(x,y) \, dA,
\\]

where \\\(dA\\\) is the area element.

- **Triple integrals:** For \\\(f(x,y,z)\\\) over volume \\\(V\\\),

\\[
\iiint_V f(x,y,z) \, dV,
\\]

where \\\(dV\\\) is the volume element.

These integrals generalize the concept of area under a curve to area and volume under surfaces and hypersurfaces.

**Coordinate Systems:**
- **Polar coordinates** are used for regions with circular symmetry in the plane: \\\((x, y) = (r \cos \theta, r \sin \theta)\\\), with area element \\\(dA = r \, dr\, d\theta\\\).
- **Cylindrical coordinates** extend polar coordinates to three dimensions: \\\((x, y, z) = (r \cos \theta, r \sin \theta, z)\\\), with volume element \\\(dV = r \, dr\, d\theta\, dz\\\).
- **Spherical coordinates** are used for problems with spherical symmetry: \\\((x, y, z) = (\rho \sin\phi \cos\theta, \rho \sin\phi \sin\theta, \rho \cos\phi)\\\), with volume element \\\(dV = \rho^2 \sin\phi \, d\rho\, d\phi\, d\theta\\\).

## Change of Variables (Jacobian Determinant)

When performing multiple integrals, changing variables simplifies integration over complex regions. The **Jacobian determinant** accounts for the distortion of area or volume elements under transformation. For a transformation \\\(\mathbf{T}(u,v) = (x(u,v), y(u,v))\\\), the Jacobian is

\\[
J = \det \begin{pmatrix}
\frac{\partial x}{\partial u} & \frac{\partial x}{\partial v} \\\\
\frac{\partial y}{\partial u} & \frac{\partial y}{\partial v}
\end{pmatrix}.
\\]

The integral transforms as

\\[
\iint_R f(x,y) \, dA = \iint_S f(x(u,v), y(u,v)) |J| \, du\, dv,
\\]

where \\\(S\\\) is the region in \\\(uv\\\)-coordinates.

In higher dimensions, the Jacobian generalizes to transformations from \\\(\mathbb{R}^n\\\) to \\\(\mathbb{R}^n\\\). For example, in three dimensions, for a transformation \\\((u, v, w) \mapsto (x(u,v,w), y(u,v,w), z(u,v,w))\\\), the Jacobian is the determinant of the matrix of all first partial derivatives. The absolute value of the Jacobian gives the local scaling factor of volume under the transformation.

## Applications in Engineering and Physics

Multivariable calculus is essential in many fields:

- **Optimization with constraints:** Using methods like Lagrange multipliers to find maxima or minima of functions subject to constraints, such as maximizing profit or minimizing energy.
- **Mass and volume calculations:** Computing mass or volume where density varies spatially, e.g., finding the mass of a non-uniform solid by integrating its density function over its volume.
- **Flux computations:** Evaluating the flow of a vector field (such as electric, magnetic, or fluid velocity fields) through a surface, fundamental in electromagnetism (Gauss's Law, Faraday's Law) and fluid dynamics.
- **Thermodynamics:** Calculating work done in thermodynamic processes, entropy changes, and heat transfer using multiple integrals and gradients.
- **Electromagnetism:** Describing electric and magnetic fields as functions of space and time, using divergence, curl, and flux integrals.
- **Economics:** Modeling utility, cost, and production functions of several variables, and using constrained optimization to maximize profit or minimize cost.

