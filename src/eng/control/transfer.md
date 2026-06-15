# Transfer Functions

A **transfer function** is the Laplace-domain ratio of output to input for an LTI system, assuming zero initial conditions:
\\[
G(s) = \frac{Y(s)}{U(s)} = \frac{b_m s^m + \cdots + b_0}{a_n s^n + \cdots + a_0}.
\\]
It captures the entire input–output behavior in one algebraic expression.

## Poles and Zeros

- **Poles** (roots of the denominator) are the system's natural modes; their location dictates stability and transient shape.
- **Zeros** (roots of the numerator) shape the response, can cause overshoot or undershoot, and can cancel poles.

A **pole-zero map** in the \\(s\\)-plane is the first thing a control engineer sketches.

## Block Diagram Algebra

Complex systems are built from blocks:

- **Series:** \\(G_1 G_2\\).
- **Parallel:** \\(G_1 + G_2\\).
- **Negative feedback:** \\(\dfrac{G}{1+GH}\\), where \\(H\\) is the feedback path.

The closed-loop **characteristic equation** is \\(1 + G(s)H(s) = 0\\).

## Second-Order Response

For \\(G(s) = \dfrac{\omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2}\\), the step response depends on \\(\zeta\\):

| Quantity | Formula |
|---|---|
| Damped frequency | \\(\omega_d = \omega_n\sqrt{1-\zeta^2}\\) |
| Percent overshoot | \\(M_p = e^{-\pi\zeta/\sqrt{1-\zeta^2}}\times100\%\\) |
| Settling time (2%) | \\(t_s \approx 4/(\zeta\omega_n)\\) |
| Peak time | \\(t_p = \pi/\omega_d\\) |

A damping ratio near \\(\zeta = 0.7\\) gives a good compromise: fast response with modest (~5%) overshoot.

## Steady-State Error

For a unity-feedback system, the **system type** (number of integrators in the open loop) sets the steady-state error to standard inputs via the static error constants \\(K_p, K_v, K_a\\). Adding an integrator (type increase) drives the step error to zero — the basis of integral control.

## Worked Example

A motor \\(G(s) = \dfrac{10}{s(s+2)}\\) in unity feedback has closed loop
\\[
T(s) = \frac{10}{s^2 + 2s + 10},
\\]
giving \\(\omega_n = \sqrt{10}\approx 3.16\\), \\(\zeta = 1/\sqrt{10}\approx 0.32\\) — underdamped with ~35% overshoot.

## See Also

- [Laplace Transform](../../signals/laplace-transform.md)
- [Stability Analysis](stability.md)
- [Frequency Response](frequency.md)
