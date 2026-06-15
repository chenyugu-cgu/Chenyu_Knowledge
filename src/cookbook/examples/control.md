# Control Recipes

Runnable recipes for simulating and tuning feedback control.

---

## Recipe 1 — Step Response of a Second-Order System

**Purpose.** Predict overshoot and settling time from \\(\omega_n\\) and \\(\zeta\\).

**Background.** For \\(G(s) = \omega_n^2/(s^2 + 2\zeta\omega_n s + \omega_n^2)\\), overshoot is \\(M_p = e^{-\pi\zeta/\sqrt{1-\zeta^2}}\\) and settling time \\(t_s \approx 4/(\zeta\omega_n)\\). See [Transfer Functions](../../eng/control/transfer.md).

**Example (Python).**
```python
import numpy as np
from scipy import signal

wn, zeta = 5.0, 0.3
sys = signal.TransferFunction([wn**2], [1, 2*zeta*wn, wn**2])
t, y = signal.step(sys)
Mp = (y.max() - 1) * 100
print(f"overshoot ≈ {Mp:.1f}%   (theory: {100*np.exp(-np.pi*zeta/np.sqrt(1-zeta**2)):.1f}%)")
```

**Result.** Simulated overshoot matches the analytic ~37% for \\(\zeta=0.3\\).

**Variations.** Sweep \\(\zeta\\) to see the over/under-damped transition; add a zero to study its effect.

---

## Recipe 2 — Simulate and Tune a PID Loop

**Purpose.** Control a first-order plant to a setpoint.

**Background.** Discrete PID: \\(u = K_p e + K_i\sum e\,\Delta t + K_d\,\Delta e/\Delta t\\). See [PID Control](../../eng/control/pid.md).

**Example (Python).**
```python
def simulate(Kp, Ki, Kd, setpoint=1.0, steps=400, dt=0.05, tau=1.0, K=2.0):
    y = 0.0; integ = 0.0; prev = setpoint
    for _ in range(steps):
        e = setpoint - y
        integ += e * dt
        deriv = (e - prev) / dt
        u = Kp*e + Ki*integ + Kd*deriv
        y += dt * (-y + K*u) / tau      # plant: tau*y' + y = K*u
        prev = e
    return y

print("final output (should approach 1.0):", round(simulate(2.0, 3.0, 0.1), 3))
```

**Result.** With integral action the steady-state error → 0 (output approaches the setpoint).

**Variations.** Add actuator saturation + anti-windup; tune with Ziegler–Nichols; add measurement noise and a derivative filter.

---

## Recipe 3 — Check Stability with Routh–Hurwitz

**Purpose.** Determine the gain range for closed-loop stability.

**Background.** A polynomial is stable iff all first-column Routh entries share a sign. See [Stability Analysis](../../eng/control/stability.md).

**Example (Python).**
```python
import numpy as np

# Characteristic polynomial s^3 + 2 s^2 + 3 s + K -> find stable K range
# Routh first column: 1, 2, (6 - K)/2, K  ->  need K>0 and K<6
for K in [1, 5, 6, 7]:
    roots = np.roots([1, 2, 3, K])
    stable = np.all(roots.real < 0)
    print(f"K={K}: stable={stable}")
```

**Result.** Stable for \\(0 < K < 6\\); confirms the Routh prediction numerically.

**Variations.** Use the root locus to visualize pole migration with \\(K\\); apply the Nyquist criterion for systems with delay.

## References

- [Transfer Functions](../../eng/control/transfer.md)
- [PID Control](../../eng/control/pid.md)
- [Stability Analysis](../../eng/control/stability.md)
