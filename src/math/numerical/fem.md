# Finite Element Methods

The finite element method (FEM) is a general and powerful technique for approximating solutions to partial differential equations (PDEs), particularly on domains with complex geometry or heterogeneous material properties. FEM is grounded in the weak (variational) formulation of differential equations and leverages the flexibility of domain discretization and basis function selection to provide systematic and convergent approximations.

## General Concept

FEM seeks to approximate the solution \\( u \\) of a boundary value problem defined on a domain \\( \\Omega \\) (possibly with boundary \\( \\partial \\Omega \\)), governed by a PDE such as
\\[
    \\mathcal{L}u = f \\quad \\text{in } \\Omega,
\\]
with suitable boundary conditions, where \\( \\mathcal{L} \\) is a differential operator and \\( f \\) is a given function. The essential idea is to represent \\( u \\) by a finite-dimensional approximation constructed from local basis functions supported on a mesh partitioning \\( \\Omega \\).

## Weak Formulation and Variational Principles

The theoretical foundation of FEM is the weak formulation of PDEs. Instead of seeking \\( u \\) satisfying the PDE pointwise, one seeks \\( u \\) in a suitable function space (typically a Sobolev space) such that
\\[
    a(u, v) = l(v) \\quad \\forall v \\in V,
\\]
where \\( a(\\cdot, \\cdot) \\) is a bilinear form associated with the operator \\( \\mathcal{L} \\), \\( l(\\cdot) \\) is a linear functional representing the right-hand side and boundary data, and \\( V \\) is the space of admissible test functions. This weak or variational formulation arises naturally from physical principles such as virtual work or minimization of energy functionals.

## Domain Discretization and Finite Elements

To render the infinite-dimensional problem computationally tractable, the domain \\( \\Omega \\) is partitioned into a finite set of non-overlapping subdomains called finite elements (e.g., triangles, quadrilaterals, tetrahedra). The collection of all elements forms a mesh, denoted \\( \\mathcal{T}_h \\), where \\( h \\) characterizes the typical element size.

## Basis Functions (Shape Functions)

On each element, one defines a set of local basis functions, commonly called shape functions, which are typically polynomials of low degree. These basis functions are chosen to have local support (nonzero only on a small number of elements) and to satisfy interpolation conditions at nodes. The global approximation space \\( V_h \\) is constructed by assembling the local basis functions:
\\[
    V_h = \\text{span}\\{ \\varphi\\_1, \\varphi\\_2, \\ldots, \\varphi\\_N \\},
\\]
where each \\( \\varphi\\_i \\) is associated with a node or degree of freedom in the mesh.

## Assembly of System Equations

The approximate solution \\( u\\_h \\in V_h \\) is sought in the form
\\[
    u\\_h = \\sum\\_{i=1}^N U\\_i \\varphi\\_i,
\\]
with unknown coefficients \\( U\\_i \\). Substituting \\( u\\_h \\) and the test functions into the weak form yields a finite-dimensional linear system:
\\[
    \\mathbf{A} \\mathbf{U} = \\mathbf{F},
\\]
where the stiffness matrix \\( \\mathbf{A} \\) has entries \\( A\\_{ij} = a(\\varphi\\_j, \\varphi\\_i) \\), and the load vector \\( \\mathbf{F} \\) has entries \\( F\\_i = l(\\varphi\\_i) \\). The assembly process involves summing contributions from each element to the global system, reflecting the local-to-global mapping of basis functions.

## Galerkin Method and Weighted Residuals

The standard FEM is a Galerkin method, in which the test functions are chosen to be the same as the basis functions for the trial space. More generally, weighted residual approaches seek \\( u\\_h \\) such that the residual of the PDE is orthogonal (in the sense of the chosen weighting functions) to the finite-dimensional test space.

## Properties of the Stiffness Matrix

The assembled stiffness matrix \\( \\mathbf{A} \\) inherits several important properties from the underlying PDE and the choice of basis functions:
- **Sparsity:** Each basis function has local support, so \\( A\\_{ij} \\) is nonzero only if \\( \\varphi\\_i \\) and \\( \\varphi\\_j \\) overlap on some element. Thus, \\( \\mathbf{A} \\) is sparse.
- **Symmetry:** For self-adjoint problems (e.g., Laplace or elasticity), \\( \\mathbf{A} \\) is symmetric: \\( A\\_{ij} = A\\_{ji} \\).
- **Positive definiteness:** For coercive problems, \\( \\mathbf{A} \\) is positive definite, ensuring existence and uniqueness of the solution.

## Convergence Theory

The mathematical theory of FEM establishes conditions under which the approximate solution \\( u\\_h \\) converges to the true solution \\( u \\) as the mesh is refined (\\( h \\to 0 \\)). Key concepts include:
- **Consistency:** The finite element space \\( V_h \\) must be rich enough that the exact solution can be approximated arbitrarily well.
- **Stability:** The discrete bilinear form must satisfy a discrete inf-sup condition or coercivity, ensuring well-posedness.
- **Error estimates:** Under regularity assumptions, the error can be bounded as
\\[
    \\|u - u\\_h\\| \\leq C h^p \\|u\\|\\_{H^{p+1}(\\Omega)},
\\]
where \\( p \\) is the degree of the polynomial basis and \\( C \\) is a constant independent of \\( h \\).

## Extensions

- **Higher-order elements:** Using polynomials of degree greater than one (e.g., quadratic, cubic) improves accuracy for smooth solutions.
- **Adaptive mesh refinement:** The mesh \\( \\mathcal{T}_h \\) can be refined locally based on a posteriori error estimates, concentrating computational effort where needed.
- **Nonlinear problems:** FEM extends to nonlinear PDEs by linearization (e.g., Newton's method) and iterative solution of the resulting nonlinear algebraic systems.
- **Time-dependent problems:** For evolution equations, FEM is combined with time discretization schemes (e.g., finite differences, Runge-Kutta methods) to handle the temporal variable.

## Applications

The finite element method is foundational in many areas of computational science and engineering, including:
- **Structural mechanics:** Analysis of stress, deformation, and stability in solids and structures.
- **Fluid dynamics:** Simulation of incompressible and compressible flows, including Navier-Stokes equations.
- **Heat transfer:** Modeling of conduction, convection, and radiation in thermal systems.
- **Electromagnetism:** Solution of Maxwell's equations in complex geometries.
- **Biomechanics:** Simulation of biological tissues and organs under mechanical and physiological loads.