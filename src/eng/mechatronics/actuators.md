# Actuators

An **actuator** converts a control signal (and energy) into physical motion or force — the output side of a mechatronic system.

## Electric Motors

The dominant actuators in robotics and automation:

| Motor | Traits |
|---|---|
| **DC brushed** | simple, cheap; brushes wear |
| **BLDC / PMSM** | efficient, high power density; needs electronic commutation |
| **Stepper** | precise open-loop positioning; can lose steps |
| **Servo** | motor + sensor + controller package |
| **AC induction** | rugged, industrial |

DC motor behavior: torque \\(\tau = k_t i\\), back-EMF \\(e = k_e\omega\\) — the coupling that makes speed control possible (see [Modeling of Systems](../control/modeling.md)).

## Other Actuation Technologies

- **Hydraulic** — very high force/power density (heavy machinery, some legged robots); needs a pump and fluid.
- **Pneumatic** — fast, compliant, clean (factory automation, soft robotics).
- **Piezoelectric** — tiny, precise, fast (nanopositioning, inkjet).
- **Shape-memory alloys / soft actuators** — compliant, biomimetic; used in some medical and soft robots.

## Driving Actuators

Motors are driven by power electronics: **H-bridges** (direction) and **PWM** (proportional control by duty cycle). BLDC/stepper motors need commutation/sequencing circuitry. These switch large currents from a small logic signal — see [Semiconductors](../electrical/semiconductors.md).

## Selection Criteria

Match actuator to required **torque/force, speed, precision, bandwidth, power, size, and environment**. Often a [gearbox](../design/power-transmission.md) adapts a fast, low-torque motor to a slow, high-torque load. Account for inertia, duty cycle, and thermal limits.

## See Also

- [Sensors](sensors.md)
- [Power Transmission](../design/power-transmission.md)
- [Robot Control](../../app/robotics/control.md)
- [Electromagnetism](../../physics/em/magnetostatics.md)
