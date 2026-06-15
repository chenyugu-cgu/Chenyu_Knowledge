# Control Systems

Control engineering designs systems that behave the way we want — a thermostat holding temperature, a drone holding altitude, a robot arm tracking a path. It rests on **feedback**: measure the output, compare it to a reference, and act on the error.

## The Feedback Loop

A standard unity-feedback loop with plant \\(G(s)\\) and controller \\(C(s)\\) has closed-loop transfer function
\\[
T(s) = \frac{C(s)G(s)}{1 + C(s)G(s)}.
\\]
The denominator \\(1 + C(s)G(s) = 0\\) is the **characteristic equation**; its roots decide stability and dynamic response.

## Why Feedback?

- **Disturbance rejection** — corrects for unmodeled loads.
- **Reference tracking** — follows a desired setpoint.
- **Reduced sensitivity** — closed-loop behavior depends less on plant parameter variation.
- **Stabilization** — can stabilize an open-loop unstable plant (inverted pendulum, rockets).

The cost is potential **instability**: too much gain or delay turns helpful correction into growing oscillation.

## Two Languages

| Classical control | Modern control |
|---|---|
| Transfer functions \\(G(s)\\) | State space \\(\dot{\mathbf{x}} = A\mathbf{x} + B\mathbf{u}\\) |
| Bode, Nyquist, root locus | Eigenvalues, controllability, observability |
| Single-input single-output | Multi-input multi-output |
| Frequency domain | Time domain / matrices |

## Chapter Map

- [Modeling of Systems](modeling.md)
- [Transfer Functions](transfer.md)
- [State-Space Representation](state-space.md)
- [Stability Analysis](stability.md)
- [Frequency Response](frequency.md)
- [PID Control](pid.md)
- [Modern Control](modern.md)
- [Optimal Control](optimal.md)

This section draws heavily on the [Laplace Transform](../../signals/laplace-transform.md) and [Linear Algebra](../../math/linear-algebra/README.md).
