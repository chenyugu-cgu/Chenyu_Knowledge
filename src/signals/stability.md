# Stability and Causality

Stability and causality decide whether a system is usable in practice. An unstable system produces unbounded outputs; a non-causal system cannot be implemented in real time. This chapter collects the criteria.

## BIBO Stability

A system is **bounded-input bounded-output (BIBO) stable** if there exists \\(M < \infty\\) such that \\(|x(t)| \le B_x \Rightarrow |y(t)| \le M\\). For an LTI system the necessary and sufficient condition is an absolutely integrable/summable impulse response:
\\[
\int_{-\infty}^{\infty} |h(t)|\, dt < \infty
\qquad\text{or}\qquad
\sum_{n=-\infty}^{\infty} |h[n]| < \infty.
\\]

## Pole-Based Stability

Stability is read directly from pole locations of the transfer function.

| Domain | Stable region | Marginal | Unstable |
|---|---|---|---|
| Continuous \\(H(s)\\) | poles in open **left half-plane** \\(\operatorname{Re}(p)<0\\) | simple poles on \\(j\omega\\)-axis | any pole with \\(\operatorname{Re}(p)>0\\) |
| Discrete \\(H(z)\\) | poles **inside unit circle** \\(|p|<1\\) | simple poles on \\(|z|=1\\) | any pole with \\(|p|>1\\) |

Repeated poles on the boundary (e.g. a double pole on the \\(j\omega\\)-axis) give unbounded growth and are **unstable**.

## Algebraic Stability Tests

When you do not want to compute roots explicitly:

- **Routh–Hurwitz** (continuous): build the Routh array from the characteristic polynomial; the system is stable iff all first-column entries have the same sign. The number of sign changes equals the number of right-half-plane poles.
- **Jury test** (discrete): the analogous tabular test for roots inside the unit circle.

### Example (Routh–Hurwitz)

For \\(s^3 + 2s^2 + 3s + K\\), the array's first column requires \\(K>0\\) and \\(6 - K > 0\\), so the closed loop is stable for \\(0 < K < 6\\).

## Causality

A system is **causal** if the output never depends on future input. For LTI systems, \\(h(t)=0\\) for \\(t<0\\) (or \\(h[n]=0\\) for \\(n<0\\)). Causality constrains the transform's **region of convergence**:

- Causal continuous system: ROC is a right half-plane, \\(\operatorname{Re}(s) > \sigma_{\max}\\).
- Causal discrete system: ROC is the exterior of a circle, \\(|z| > r_{\max}\\).

A causal LTI system is stable iff its ROC includes the \\(j\omega\\)-axis (continuous) or the unit circle (discrete).

## Marginal Stability and Oscillation

Systems with poles exactly on the stability boundary (an ideal LC oscillator, a pure integrator) are **marginally stable**: bounded inputs may produce sustained or linearly growing outputs. These are useful for oscillator design but require care in control loops.

## See Also

- [System Properties](system-properties.md)
- [Stability Analysis](../eng/control/stability.md) — Routh, root locus, Nyquist in control context.
- [Z-Transform](z-transform.md)
