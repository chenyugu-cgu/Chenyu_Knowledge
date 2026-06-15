# Human-Robot Interaction

Human-Robot Interaction (HRI) studies how people and robots communicate, collaborate, and share space safely. As robots leave cages and enter homes, hospitals, and factories alongside people, HRI becomes as important as the underlying mechanics.

## Safety First

When robots share space with humans, safety is paramount:
- **Collaborative robots (cobots)** use force/torque sensing to detect contact and stop or yield.
- **Speed and separation monitoring** slows the robot as people approach.
- **Power and force limiting** caps the energy a robot can impart.

These are codified in standards (ISO 10218, ISO/TS 15066). Compliance and [impedance control](control.md) make physical interaction inherently gentle.

## Modes of Interaction

| Mode | Example |
|---|---|
| Teleoperation | surgeon controls a surgical robot |
| Supervised autonomy | human sets goals, robot executes |
| Collaboration | human and robot share a task |
| Social interaction | robot communicates via speech/gesture |

## Communication Channels

Robots convey intent through motion (legible trajectories), displays, lights, speech, and gesture; they perceive humans through [vision](../../cs/vision/README.md) (pose, gaze, expression), speech recognition, and force. **Legibility** — motion that clearly signals intent — reduces surprise and builds trust.

## Physical Human-Robot Interaction (pHRI)

Direct contact tasks — rehabilitation robots, [exoskeletons](../biomechanics/prosthetics.md), and hand-guiding — require controllers that are simultaneously **compliant** (safe, comfortable) and **assistive** (effective). Admittance/impedance control and intent estimation (often from [EMG](../biomed/biosignals.md) or force) are central.

## Trust, Autonomy, and Ethics

Effective collaboration depends on **calibrated trust** — neither over- nor under-relying on the robot. Transparency, predictability, and clear handoff of control matter. Autonomy raises ethical and accountability questions, especially in healthcare and autonomous vehicles.

## Applications

Manufacturing cobots, surgical and rehabilitation robotics, assistive and service robots, and autonomous vehicles interacting with pedestrians.

## See Also

- [Robot Control](control.md) — compliance and impedance.
- [Rehabilitation Devices](../biomed/rehab.md)
- [Sensing and Perception](sensing.md)
