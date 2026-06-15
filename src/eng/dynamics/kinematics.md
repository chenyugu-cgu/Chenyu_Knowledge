# Kinematics

Kinematics describes motion — position, velocity, and acceleration — without reference to the forces that cause it. It is pure geometry plus time.

## Rectilinear Motion

For motion along a line with position \\(s(t)\\),
\\[
v = \frac{ds}{dt}, \qquad a = \frac{dv}{dt} = \frac{d^2 s}{dt^2}, \qquad a\,ds = v\,dv.
\\]
The last (separable) relation is invaluable when acceleration depends on position rather than time.

### Constant Acceleration

When \\(a\\) is constant,
\\[
v = v_0 + a t, \quad
s = s_0 + v_0 t + \tfrac{1}{2}a t^2, \quad
v^2 = v_0^2 + 2a(s - s_0).
\\]
These are the everyday "SUVAT" equations (projectiles, braking distance, free fall with \\(a=g\\)).

## Curvilinear Motion

In two or three dimensions the velocity is tangent to the path and the acceleration has two parts in **normal–tangential** coordinates:
\\[
a_t = \frac{dv}{dt}\ (\text{speeding up/down}), \qquad
a_n = \frac{v^2}{\rho}\ (\text{turning}),
\\]
where \\(\rho\\) is the radius of curvature. The total acceleration is \\(a = \sqrt{a_t^2 + a_n^2}\\). Even at constant speed, a turning body accelerates (centripetally).

## Projectile Motion

With gravity only, horizontal and vertical motions decouple:
\\[
x = v_0\cos\theta\,t, \qquad y = v_0\sin\theta\,t - \tfrac{1}{2}g t^2.
\\]
Range on flat ground is \\(R = \dfrac{v_0^2 \sin 2\theta}{g}\\), maximized at \\(\theta = 45^\circ\\).

## Rotational Kinematics

For rotation about a fixed axis, angular position \\(\theta\\), angular velocity \\(\omega = \dot\theta\\), and angular acceleration \\(\alpha = \dot\omega\\) mirror the linear equations. A point at radius \\(r\\) has
\\[
v = r\omega, \qquad a_t = r\alpha, \qquad a_n = r\omega^2.
\\]

## Relative Motion

The velocity of \\(B\\) relative to \\(A\\) is \\(\mathbf{v}_{B} = \mathbf{v}_{A} + \mathbf{v}_{B/A}\\). For a rotating frame with angular velocity \\(\boldsymbol{\omega}\\), velocities and accelerations pick up Coriolis and transport terms — the basis of mechanism analysis and rotating-frame dynamics.

## See Also

- [Newton's Laws](newton.md)
- [Robot Kinematics](../../app/robotics/kinematics.md)
