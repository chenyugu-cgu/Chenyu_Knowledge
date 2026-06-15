# Power Transmission

Power transmission delivers torque and speed from a source (motor, engine) to where work is done, usually changing the speed/torque ratio along the way.

## The Fundamental Trade

Power is conserved (minus losses), so changing speed inversely changes torque:
\\[
P = T\omega = \text{const} \;\Rightarrow\; \frac{T_2}{T_1} = \frac{\omega_1}{\omega_2}.
\\]
A reducer trades speed for torque — exactly what motors (fast, low torque) need to drive loads (slow, high torque).

## Gears

Meshing gears give an exact ratio set by tooth counts:
\\[
\frac{\omega_1}{\omega_2} = \frac{N_2}{N_1}.
\\]
Types: spur (parallel shafts), helical (smoother, higher load), bevel (intersecting shafts), worm (high reduction, often self-locking), and planetary (compact, high ratio). Gears are sized against tooth bending (Lewis equation) and surface fatigue (pitting).

## Belts and Chains

- **Belts** (V, timing) — quiet, tolerant of misalignment, can slip (or not, for toothed timing belts). Ratio by pulley diameters.
- **Chains** — positive engagement, high load, used where slip is unacceptable (bicycles, cam drives).

## Couplings and Clutches

- **Couplings** connect shafts, accommodating misalignment (flexible) or not (rigid).
- **Clutches** engage/disengage drive; **brakes** dissipate kinetic energy as heat (friction analysis — see [Friction](../statics/friction.md)).

## Efficiency

Each stage loses power to friction and meshing. Gear trains are typically 95–99% efficient per stage; worm drives much less. Losses become heat — connecting to [heat transfer](../heat-transfer/README.md).

## Selection

Choose the drive from required ratio, torque, speed, space, noise, and cost. Gearmotors and gearboxes are usually selected from catalogs by rated torque and service factor.

## See Also

- [Machine Elements](machine-elements.md)
- [Mechanisms and Linkages](mechanisms.md)
- [Actuators](../mechatronics/actuators.md)
