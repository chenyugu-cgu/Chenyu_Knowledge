# Statics and Dynamics Recipes

Worked recipes spanning equilibrium analysis, projectile motion, and vibration.

---

## Recipe 1 — Reactions of a Simply Supported Beam

**Purpose.** Find support reactions for a beam under point loads.

**Background.** Apply 2-D equilibrium \\(\sum F_y = 0\\), \\(\sum M = 0\\). See [Forces and Equilibrium](../../eng/statics/equilibrium.md).

**Method.** Take moments about one support to isolate the other reaction, then sum vertical forces.

**Example (Python).**
```python
# Beam length L with point loads (position, magnitude downward)
L = 10.0
loads = [(3.0, 500.0), (7.0, 800.0)]   # (x from A, N)

# Sum moments about A:  R_B * L = sum(P_i * x_i)
R_B = sum(P*x for x, P in loads) / L
R_A = sum(P for _, P in loads) - R_B
print(f"R_A = {R_A:.1f} N, R_B = {R_B:.1f} N")   # R_A=730.0, R_B=570.0
```

**Result.** \\(R_A = 730\\) N, \\(R_B = 570\\) N; their sum equals the total load (1300 N).

**Variations.** Add distributed loads (replace by resultant at centroid); handle overhangs and cantilevers.

---

## Recipe 2 — Projectile Range and Trajectory

**Purpose.** Compute the flight of a projectile under gravity.

**Background.** Horizontal and vertical motions decouple; range on flat ground is \\(R = v_0^2\sin 2\theta / g\\). See [Kinematics](../../eng/dynamics/kinematics.md).

**Example (Python).**
```python
import numpy as np

g, v0, theta = 9.81, 30.0, np.radians(40)
t_flight = 2*v0*np.sin(theta)/g
R = v0**2 * np.sin(2*theta) / g
h_max = (v0*np.sin(theta))**2 / (2*g)
print(f"flight time={t_flight:.2f}s, range={R:.1f}m, apex={h_max:.1f}m")
```

**Result.** For \\(v_0=30\\) m/s at 40°: range ≈ 90.3 m, apex ≈ 19.0 m.

**Variations.** Add air drag (numerically integrate \\(m\ddot{\mathbf{r}} = m\mathbf{g} - b\mathbf{v}\\)); solve for the launch angle hitting a target.

---

## Recipe 3 — Free Vibration of a Mass–Spring–Damper

**Purpose.** Simulate and characterize a damped oscillator.

**Background.** \\(\ddot{x} + 2\zeta\omega_n\dot{x} + \omega_n^2 x = 0\\), with \\(\omega_n=\sqrt{k/m}\\), \\(\zeta = c/(2\sqrt{km})\\). See [Vibrations](../../eng/dynamics/vibrations.md).

**Example (Python).**
```python
import numpy as np
from scipy.integrate import solve_ivp

m, k, c = 1.0, 100.0, 4.0
wn = np.sqrt(k/m); zeta = c/(2*np.sqrt(k*m))

def f(t, y): return [y[1], -(c/m)*y[1] - (k/m)*y[0]]
sol = solve_ivp(f, [0, 5], [1.0, 0.0], dense_output=True, max_step=0.01)
print(f"wn={wn:.2f} rad/s, zeta={zeta:.3f} ({'under' if zeta<1 else 'over'}damped)")
```

**Result.** \\(\omega_n = 10\\) rad/s, \\(\zeta = 0.2\\) — underdamped, decaying oscillation at \\(\omega_d = \omega_n\sqrt{1-\zeta^2}\\).

**Variations.** Add harmonic forcing to study resonance; sweep \\(\zeta\\) across under/critical/overdamped regimes.

## References

- [Forces and Equilibrium](../../eng/statics/equilibrium.md)
- [Newton's Laws](../../eng/dynamics/newton.md)
- [Vibrations](../../eng/dynamics/vibrations.md)
