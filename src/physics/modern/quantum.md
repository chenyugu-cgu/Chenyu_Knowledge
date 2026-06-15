# Quantum Mechanics

Quantum mechanics governs matter at atomic scales, where energy is quantized and particles behave as waves. It is the foundation of chemistry, electronics, and modern materials.

## The Wavefunction

A particle's state is a complex **wavefunction** \\(\psi(x,t)\\); \\(|\psi|^2\\) is the probability density of finding it at \\(x\\). The wavefunction evolves by the **Schrödinger equation**:
\\[
i\hbar\frac{\partial\psi}{\partial t} = \hat{H}\psi, \qquad
\hat{H} = -\frac{\hbar^2}{2m}\nabla^2 + V(\mathbf{r}).
\\]
For stationary states, the time-independent form \\(\hat{H}\psi = E\psi\\) is an eigenvalue problem whose eigenvalues are the allowed energies.

## Quantization

Confining a particle quantizes its energy. The **particle in a box** has levels
\\[
E_n = \frac{n^2\pi^2\hbar^2}{2mL^2}, \quad n = 1, 2, \dots
\\]
Discrete energy levels explain atomic spectra, the stability of atoms, and the colors of materials.

## Key Principles

- **Superposition** — states add; measurement collapses to an eigenstate.
- **Heisenberg uncertainty** — \\(\Delta x\,\Delta p \ge \hbar/2\\); position and momentum cannot both be sharp.
- **Tunneling** — particles penetrate classically forbidden barriers (the basis of the scanning tunneling microscope and flash memory).
- **Spin** — intrinsic angular momentum; the basis of [MRI](../../app/biomed/imaging.md) and magnetic materials.

## Operators and Observables

Physical quantities are Hermitian **operators**; their eigenvalues are the possible measurements and expectation values give averages. This linear-algebraic structure ([eigenvalues](../../math/linear-algebra/eigen.md), Hilbert spaces) is why linear algebra is the language of quantum theory.

## Engineering Payoff

Lasers (stimulated emission), semiconductors and transistors (band theory), MRI (nuclear spin), quantum dots, and emerging quantum computing all derive directly from these principles.

## See Also

- [Solid-State Physics](solid-state.md)
- [Series Solutions](../../math/diffeq/series-solutions.md) — special functions of the Schrödinger equation.
- [Eigenvalues and Eigenvectors](../../math/linear-algebra/eigen.md)
