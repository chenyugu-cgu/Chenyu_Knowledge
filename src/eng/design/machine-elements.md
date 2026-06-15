# Machine Elements

Machine elements are the standardized building blocks of mechanical systems. Knowing how to size them is the core of practical mechanical design.

## Shafts

Shafts transmit torque and carry bending loads. They are sized for combined stress and checked against fatigue and critical (whirling) speed. Torsional stress \\(\tau = Tr/J\\) and bending \\(\sigma = Mc/I\\) combine via a failure theory (von Mises). See [Torsion](../materials/torsion.md) and [Failure Theories](../materials/failure.md).

## Springs

Helical springs store energy. The stiffness of a round-wire compression spring:
\\[
k = \frac{G d^4}{8 D^3 N},
\\]
where \\(d\\) is wire diameter, \\(D\\) coil diameter, \\(N\\) active coils, \\(G\\) the shear modulus. Springs are checked for shear stress and buckling.

## Fasteners and Joints

- **Bolts/screws** — sized for tensile preload and shear; tightened to a target preload \\(F_i\\) so joints don't separate or slip under load.
- **Welds and adhesives** — analyzed for shear/peel over the bond area.
- **Rivets and pins** — shear- and bearing-stress limited.

Preloaded bolted joints carry fluctuating load largely through the clamped members, dramatically improving fatigue life.

## Bearings

- **Rolling-element bearings** — sized by dynamic load rating; life follows \\(L_{10} = (C/P)^{p}\\) (\\(p=3\\) for ball bearings).
- **Journal (sliding) bearings** — rely on a hydrodynamic oil film (Reynolds equation), linking to [fluid mechanics](../fluid/internal.md).

## Other Elements

Keys and splines (torque transfer), seals, clutches and brakes (friction), and couplings (shaft connection, misalignment tolerance).

## Design Philosophy

Use standard sizes and rated catalog components wherever possible — they are cheaper, available, and characterized. Custom parts are reserved for where standards won't do.

## See Also

- [Power Transmission](power-transmission.md)
- [Failure Theories](../materials/failure.md)
- [Tolerancing and GD&T](tolerancing.md)
