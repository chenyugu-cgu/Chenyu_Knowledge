# PID Control

The **proportional–integral–derivative (PID)** controller is the workhorse of industry — over 90% of control loops are PID. It needs no model, has three intuitive knobs, and works remarkably well.

## The PID Law

The control signal is
\\[
u(t) = K_p\, e(t) + K_i \int_0^t e(\tau)\,d\tau + K_d\,\frac{de(t)}{dt},
\\]
where \\(e(t) = r(t) - y(t)\\) is the error. In the Laplace domain,
\\[
C(s) = K_p + \frac{K_i}{s} + K_d s.
\\]

## What Each Term Does

| Term | Effect | Watch out for |
|---|---|---|
| **Proportional** \\(K_p\\) | faster response, reduces error | too high → oscillation; leaves steady-state offset |
| **Integral** \\(K_i\\) | eliminates steady-state error | adds lag; causes overshoot and **windup** |
| **Derivative** \\(K_d\\) | adds damping, anticipates error | amplifies measurement noise |

## Tuning

**Ziegler–Nichols (ultimate gain):** increase \\(K_p\\) until sustained oscillation at gain \\(K_u\\) and period \\(T_u\\), then set

| Controller | \\(K_p\\) | \\(K_i\\) | \\(K_d\\) |
|---|---|---|---|
| P | \\(0.5K_u\\) | — | — |
| PI | \\(0.45K_u\\) | \\(K_p/(0.83T_u)\\) | — |
| PID | \\(0.6K_u\\) | \\(K_p/(0.5T_u)\\) | \\(K_p(0.125T_u)\\) |

Modern practice often tunes by simulation or model-based methods (IMC, pole placement) for tighter, more robust loops.

## Practical Refinements

- **Derivative filtering:** replace \\(K_d s\\) with \\(\dfrac{K_d s}{1 + s/N}\\) to limit noise gain.
- **Anti-windup:** clamp or back-calculate the integrator when the actuator saturates.
- **Setpoint weighting / derivative-on-measurement:** avoid "derivative kick" on step setpoint changes.

## Discrete Implementation

```python
class PID:
    def __init__(self, kp, ki, kd, dt):
        self.kp, self.ki, self.kd, self.dt = kp, ki, kd, dt
        self.integral = 0.0
        self.prev_error = 0.0

    def step(self, setpoint, measurement):
        error = setpoint - measurement
        self.integral += error * self.dt
        derivative = (error - self.prev_error) / self.dt
        self.prev_error = error
        return self.kp*error + self.ki*self.integral + self.kd*derivative
```

## See Also

- [Transfer Functions](transfer.md)
- [Frequency Response](frequency.md)
- [Control Recipes](../../cookbook/examples/control.md)
