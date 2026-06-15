# Partial Differential Equations

Partial differential equations (PDEs) involve a function of several variables and its partial derivatives. They govern fields that vary in space and time — temperature, displacement, voltage, pressure, probability.

## The Three Canonical Linear PDEs

| Type | Equation | Models |
|---|---|---|
| Parabolic — **heat/diffusion** | \\(u_t = \alpha\nabla^2 u\\) | conduction, diffusion |
| Hyperbolic — **wave** | \\(u_{tt} = c^2\nabla^2 u\\) | vibration, sound, EM waves |
| Elliptic — **Laplace/Poisson** | \\(\nabla^2 u = 0\\) (or \\(=f\\)) | steady state, potentials |

These classify by the discriminant of the second-order terms and dictate which boundary/initial conditions are well-posed.

## Separation of Variables

The workhorse analytic method: assume a product solution \\(u(x,t) = X(x)T(t)\\). Substituting separates the PDE into ODEs for \\(X\\) and \\(T\\) linked by a separation constant. Boundary conditions quantize the constant into **eigenvalues**, and the full solution is a **Fourier series** of the resulting modes.

**Example (heat equation on a rod, ends held at 0):**
\\[
u(x,t) = \sum_{n=1}^{\infty} b_n \sin\!\frac{n\pi x}{L}\, e^{-\alpha (n\pi/L)^2 t},
\\]
with \\(b_n\\) the Fourier sine coefficients of the initial temperature.

## Boundary and Initial Conditions

- **Dirichlet** — value prescribed on the boundary.
- **Neumann** — derivative (flux) prescribed.
- **Robin/mixed** — a combination (e.g. convective cooling).

Well-posedness (existence, uniqueness, stability) depends on matching the right conditions to the PDE type.

## Other Solution Routes

- **Fourier / Laplace transforms** convert PDEs on infinite domains into ODEs.
- **Method of characteristics** solves first-order and hyperbolic PDEs along curves.
- **Green's functions** build solutions from the response to a point source.
- **Numerical methods** (finite difference, [finite element](../numerical/fem.md), spectral) handle complex geometries — see [Numerical PDEs](../numerical/pdes.md).

## Applications

Heat conduction ([Heat Transfer](../../eng/heat-transfer/README.md)), structural vibration, fluid flow ([Navier–Stokes](../../eng/fluid/conservation.md)), electrostatics ([Electromagnetism](../../physics/em/maxwell.md)), and the Schrödinger equation ([Quantum Mechanics](../../physics/modern/quantum.md)).

## See Also

- [The Wave Equation](../../physics/optics/wave-equation.md)
- [Fourier Series](../../signals/fourier-series.md)
- [Finite Element Methods](../numerical/fem.md)
