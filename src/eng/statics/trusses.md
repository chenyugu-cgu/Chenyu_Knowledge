# Trusses and Frames

A **truss** is a structure of straight two-force members connected at frictionless pin joints and loaded only at the joints. Each member therefore carries pure **tension** or **compression**. Bridges, roofs, cranes, and towers are trusses.

## Idealizing Assumptions

1. Members are connected by smooth pins (no moment transfer).
2. Loads and reactions act only at joints.
3. Member weight is negligible or split to its end joints.

Under these assumptions every member is a two-force member.

## Determinacy

A planar truss with \\(m\\) members, \\(r\\) reactions, and \\(j\\) joints is statically determinate when
\\[
m + r = 2j.
\\]
If \\(m + r < 2j\\) the truss is a mechanism (unstable); if \\(m + r > 2j\\) it is statically indeterminate.

## Method of Joints

Isolate each joint and apply \\(\sum F_x = 0,\ \sum F_y = 0\\) (only two equations per joint, since all forces are concurrent). Start at a joint with at most two unknowns and work through the structure. A positive result means **tension** (member pulls the joint), negative means **compression**.

### Zero-Force Members

Quick rules that simplify analysis:
- At an unloaded joint with **two non-collinear members**, both are zero-force.
- At an unloaded joint with **three members, two collinear**, the third is zero-force.

## Method of Sections

To find a few specific member forces, cut the truss through (at most three unknown members) and treat one side as a rigid body with all three equilibrium equations \\(\sum F_x, \sum F_y, \sum M\\). Choosing the moment center at the intersection of two unknowns isolates the third directly. This is far faster than the method of joints when only interior members are of interest.

## Worked Example (Method of Joints)

For a joint where a horizontal member \\(F_{AB}\\) and a diagonal at \\(30^\circ\\) carrying \\(F_{AC}\\) support a downward load \\(P\\):
\\[
\sum F_y = 0:\ F_{AC}\sin 30^\circ - P = 0 \Rightarrow F_{AC} = 2P\ (\text{tension}),
\\]
\\[
\sum F_x = 0:\ F_{AB} + F_{AC}\cos 30^\circ = 0 \Rightarrow F_{AB} = -\sqrt{3}\,P\ (\text{compression}).
\\]

## Frames and Machines

**Frames** (stationary, support loads) and **machines** (transmit/modify forces) contain at least one **multi-force member**, so members are not simple tension/compression. Analyze by dismembering the structure, drawing an FBD of each member, and applying equilibrium with Newton's third law at each connecting pin.

## See Also

- [Forces and Equilibrium](equilibrium.md)
- [Axial Loading](../materials/axial.md) — sizing truss members for stress.
