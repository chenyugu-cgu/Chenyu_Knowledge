# Manipulation and Grasping

Manipulation is how robots physically interact with objects — picking, placing, assembling, and using tools. It combines [kinematics](kinematics.md), [dynamics](dynamics.md), [control](control.md), and [perception](sensing.md).

## Grasping

A **grasp** must hold an object against expected disturbances. Key ideas:
- **Force closure** — the contacts can resist any external wrench (force + torque).
- **Form closure** — geometry alone immobilizes the object (no friction needed).
- **Grasp quality metrics** rank candidate grasps by stability margin.

Friction matters: the **friction cone** at each contact bounds the forces a finger can apply without slipping (see [Friction](../../eng/statics/friction.md)).

## End Effectors

| Type | Trait |
|---|---|
| Parallel-jaw gripper | simple, reliable, limited shapes |
| Multi-fingered hand | dexterous, complex to control |
| Suction | great for flat/smooth surfaces |
| Soft grippers | compliant, forgiving of error |

## Manipulation Planning

Beyond reaching a pose, manipulation plans the **sequence** of contacts and motions: pre-grasp approach, grasp, lift, transport, place. It must respect collisions, joint limits, and the object's dynamics — a constrained [motion-planning](planning.md) problem.

## Force and Compliance Control

Contact tasks (insertion, polishing, assembly) require regulating **force**, not just position. **Impedance/admittance control** makes the arm behave like a tunable spring–damper, and **hybrid force/position control** commands force in constrained directions — see [Robot Control](control.md). Compliance prevents damage when position error meets a rigid environment.

## Perception for Manipulation

Grasping unknown objects needs [3-D vision](../../cs/vision/3d-vision.md) to estimate shape and pose. **Learned grasping** — predicting grasp points from images/point clouds with [deep networks](../../cs/ml/deep-learning.md) — now handles cluttered, novel objects, and [reinforcement learning](../../cs/ml/rl.md) tackles dexterous in-hand manipulation.

## Applications

Industrial assembly and bin-picking, warehouse order fulfillment, surgical robotics, and assistive/household robots.

## See Also

- [Robot Control](control.md)
- [3D Vision](../../cs/vision/3d-vision.md)
- [Friction](../../eng/statics/friction.md)
