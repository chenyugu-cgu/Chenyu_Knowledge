# Failure Theories

A part "fails" when it can no longer perform its function — by yielding, fracturing, buckling, or fatiguing. Failure theories predict the onset of failure under combined loading from simple uniaxial test data.

## Yield Criteria (Ductile Materials)

Ductile materials fail by yielding. Two criteria dominate, expressed in terms of principal stresses \\(\sigma_1, \sigma_2, \sigma_3\\) and yield strength \\(\sigma_y\\):

**Maximum shear stress (Tresca):**
\\[
\tau_{\max} = \frac{\sigma_1 - \sigma_3}{2} \ge \frac{\sigma_y}{2}.
\\]

**Distortion energy (von Mises)** — usually closer to experiment:
\\[
\sigma_{vM} = \sqrt{\tfrac{1}{2}\big[(\sigma_1-\sigma_2)^2 + (\sigma_2-\sigma_3)^2 + (\sigma_3-\sigma_1)^2\big]} \ge \sigma_y.
\\]
For plane stress the von Mises stress reduces to \\(\sigma_{vM} = \sqrt{\sigma_x^2 - \sigma_x\sigma_y + \sigma_y^2 + 3\tau_{xy}^2}\\).

## Fracture Criteria (Brittle Materials)

Brittle materials fail by fracture with little yielding. The **maximum normal stress** theory predicts failure when \\(\sigma_1\\) reaches the ultimate strength. **Mohr's** (Coulomb–Mohr) theory accounts for different tensile and compressive strengths.

## Fatigue

Most machine failures are **fatigue**: cracks grow under cyclic loading well below the static strength. The **S–N curve** plots stress amplitude vs. cycles to failure; steels show an **endurance limit** below which life is effectively infinite. The **Goodman** relation combines mean and alternating stress:
\\[
\frac{\sigma_a}{S_e} + \frac{\sigma_m}{\sigma_u} = \frac{1}{n}.
\\]
Stress concentrations, surface finish, and corrosion drastically reduce fatigue life.

## Fracture Mechanics

When a crack of length \\(a\\) is present, failure occurs when the **stress-intensity factor** reaches the material's fracture toughness:
\\[
K_I = Y\,\sigma\sqrt{\pi a} \ge K_{IC}.
\\]
This explains why large structures fail at stresses far below yield once flaws exist.

## Buckling (Stability Failure)

Slender columns fail by **buckling** before reaching the yield stress. The Euler critical load is
\\[
P_{cr} = \frac{\pi^2 E I}{(K L)^2},
\\]
where \\(KL\\) is the effective length (\\(K=1\\) pinned–pinned, \\(0.5\\) fixed–fixed, \\(2\\) cantilever). Buckling is governed by stiffness \\(EI\\) and geometry, **not** by material strength.

## See Also

- [Stress and Strain](stress-strain.md) — principal stresses and Mohr's circle.
- [Bending and Shear](bending.md)
- [Mechanical Properties](../../app/materials-science/properties.md)
