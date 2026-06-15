# Musculoskeletal Modeling

Musculoskeletal modeling represents the body as a system of bones (rigid links), joints, and muscles (actuators) to compute internal forces that cannot be measured directly — muscle and joint loads during movement.

## The Model

The skeleton is modeled as articulated rigid bodies (like a [robot linkage](../robotics/kinematics.md)); muscles are force-producing actuators that span joints with specific paths and moment arms. Tools like OpenSim assemble subject-scaled models from anatomy.

## Muscle Mechanics: The Hill Model

Muscle force depends on activation, length, and velocity, captured by the **Hill-type** model:
\\[
F = a\,f_L(\ell)\,f_V(\dot\ell)\,F_{\max} + F_{\text{passive}}(\ell),
\\]
where \\(a\\) is activation (0–1), \\(f_L\\) the force–length, and \\(f_V\\) the force–velocity relation. Muscles are strongest at optimal length and weaken as they shorten faster (the force–velocity curve).

## The Redundancy Problem

Many muscles cross each joint, so the joint moment under-determines individual muscle forces. **Static optimization** resolves this by minimizing a cost (e.g. summed squared activation) subject to producing the required moments:
\\[
\min \sum_i a_i^2 \quad\text{s.t.}\quad \sum_i r_i F_i = M_{\text{joint}}.
\\]
This is a constrained [optimization](../../cs/optimization/constrained.md) problem solved at each instant.

## Inverse vs. Forward Dynamics

- **Inverse dynamics** — from measured motion + external forces, compute joint moments (see [Human Motion](motion.md)), then muscle forces by optimization.
- **Forward dynamics** — from muscle activations (e.g. [EMG](../biomed/biosignals.md)-driven), simulate the resulting motion.

## Applications

- Surgical planning (tendon transfers, joint replacement).
- Estimating **joint contact forces** for implant design.
- Sports performance and rehabilitation.
- Driving [prosthetic and exoskeleton](prosthetics.md) control.

## See Also

- [Human Motion](motion.md)
- [Constrained Optimization](../../cs/optimization/constrained.md)
- [Robot Dynamics](../robotics/dynamics.md)
