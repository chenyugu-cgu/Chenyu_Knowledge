# Statics

Statics is the branch of mechanics that studies bodies **at rest or in uniform motion**, where the net force and net moment are zero. It is the foundation of structural and machine design: before anything moves, it must first be held in equilibrium, and the forces that hold it determine whether it will survive.

## Core Idea

A rigid body is in **static equilibrium** when
\\[
\sum \mathbf{F} = \mathbf{0}, \qquad \sum \mathbf{M}_O = \mathbf{0}
\\]
about any point \\(O\\). In two dimensions these reduce to three scalar equations \\(\sum F_x = 0,\ \sum F_y = 0,\ \sum M = 0\\); in three dimensions, six.

## What This Section Covers

- [Forces and Equilibrium](equilibrium.md) — free-body diagrams, resultants, equilibrium equations, supports and reactions.
- [Trusses and Frames](trusses.md) — method of joints, method of sections, determinacy.
- [Friction](friction.md) — Coulomb friction, wedges, belts, impending motion.
- [Center of Gravity](center-mass.md) — centroids, composite bodies, distributed loads.

## The Statics Workflow

1. **Isolate** the body and draw a **free-body diagram (FBD)** showing every external force and reaction.
2. Choose convenient axes and a **moment center** (often where unknowns intersect, to eliminate them).
3. Write the equilibrium equations.
4. Solve the linear system for the unknown reactions and member forces.
5. Check determinacy: a 2-D rigid body has 3 equations, so at most 3 unknown reactions are solvable by statics alone (otherwise the problem is **statically indeterminate** and needs material compatibility — see [Strength of Materials](../materials/README.md)).

Mastering the FBD is 80% of statics. Every recipe in this section begins with one.
