# Crystal Structures

Most engineering metals and ceramics are **crystalline** — atoms arranged in a periodic lattice. The lattice type and its defects largely determine mechanical, thermal, and electrical behavior.

## The Crystal Lattice

A crystal is a **unit cell** repeated in three dimensions. The 14 Bravais lattices classify all periodic arrangements. The most common metallic structures:

| Structure | Atoms/cell | Packing factor | Examples |
|---|---|---|---|
| BCC (body-centered cubic) | 2 | 0.68 | Fe (α), W, Cr |
| FCC (face-centered cubic) | 4 | 0.74 | Al, Cu, Ni, Au |
| HCP (hexagonal close-packed) | 6 | 0.74 | Mg, Ti, Zn |

The **atomic packing factor (APF)** is the fraction of space filled by atoms; FCC and HCP are close-packed (0.74, the maximum).

## Miller Indices

Crystallographic planes \\((hkl)\\) and directions \\([uvw]\\) are labeled by **Miller indices**, derived from intercepts with the axes. Slip — the mechanism of plastic deformation — occurs preferentially on close-packed planes and directions, which is why FCC metals (many slip systems) are so ductile.

## Crystal Defects

Real crystals are imperfect, and defects govern properties:

- **Point defects** — vacancies and interstitials; drive diffusion.
- **Line defects (dislocations)** — enable plastic deformation at stresses far below the theoretical strength. Their motion **is** ductility.
- **Planar defects** — grain boundaries and stacking faults; impede dislocations (strengthening).
- **Volume defects** — voids, inclusions, cracks.

## Strengthening Mechanisms

All strengthening works by impeding dislocation motion:
- **Grain refinement** — more boundaries (Hall–Petch: \\(\sigma_y = \sigma_0 + k d^{-1/2}\\)).
- **Solid-solution** — alloying atoms strain the lattice.
- **Work hardening** — dislocations tangle.
- **Precipitation hardening** — second-phase particles block slip.

## Diffusion

Atomic transport follows Fick's laws; the diffusion coefficient is thermally activated:
\\[
D = D_0\,e^{-Q/RT}.
\\]
Diffusion governs heat treatment, doping, creep, and sintering.

## See Also

- [Mechanical Properties](properties.md)
- [Semiconductors](../../eng/electrical/semiconductors.md)
- [Pure Substances](../../eng/thermo/substances.md) — phase diagrams.
