# Human Motion

Human movement analysis quantifies how the body moves and the forces behind it — the foundation of gait analysis, sports biomechanics, and rehabilitation.

## The Body as a Linkage

The musculoskeletal system is modeled as rigid **segments** (foot, shank, thigh, trunk…) connected by **joints**, much like a [robotic linkage](../robotics/kinematics.md). Each segment has mass, a center of mass, and a moment of inertia, estimated from anthropometric tables scaled to the subject.

## Motion Capture

- **Optical systems** track reflective markers with multiple cameras to reconstruct 3-D positions.
- **Inertial measurement units (IMUs)** estimate orientation from accelerometers and gyroscopes — portable and marker-free.
- **Video + pose estimation** (deep learning) increasingly enables markerless capture.

Joint angles are computed from segment orientations; velocities and accelerations by differentiation (with filtering to suppress noise).

## Inverse Dynamics

The core computation: given segment kinematics and external forces (ground reaction from force plates), compute the net **joint moments** and forces by applying Newton–Euler equations from the distal segment inward:
\\[
\sum \mathbf{M}_{\text{joint}} = I\boldsymbol{\alpha} - \mathbf{M}_{\text{external}}.
\\]
These moments reveal which muscle groups dominate each phase of movement.

## The Gait Cycle

Walking is analyzed over one **gait cycle** (heel strike to next heel strike of the same foot), split into **stance** (~60%) and **swing** (~40%) phases. Standard outputs:
- joint angle trajectories (hip, knee, ankle),
- ground reaction force (the characteristic double-hump vertical curve),
- joint moments and powers.

Deviations from normal patterns flag pathology and guide treatment.

## Muscle Forces and EMG

Joint moments are produced by many muscles crossing each joint — a redundant system. **Electromyography (EMG)** measures activation timing, and **static optimization** distributes moments among muscles (e.g. minimizing summed squared activation) subject to physiological limits.

## See Also

- [Joint Modeling](joints.md)
- [Kinematics](../../eng/dynamics/kinematics.md)
- [Robot Kinematics](../robotics/kinematics.md)
