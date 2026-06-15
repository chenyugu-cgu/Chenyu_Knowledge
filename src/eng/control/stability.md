# Stability Analysis

A control system is useless if unstable. Stability analysis determines whether the closed-loop poles lie in the stable region and how much margin remains before instability.

## Stability Definition

For an LTI system, **BIBO stability** requires all closed-loop poles in the open left half-plane (continuous) or inside the unit circle (discrete). The poles are the roots of the characteristic equation \\(1 + G(s)H(s) = 0\\).

## Routh–Hurwitz Criterion

Determine stability **without computing roots**. Build the Routh array from the characteristic polynomial coefficients; the system is stable iff all entries in the first column are positive. The number of sign changes equals the number of right-half-plane poles.

### Example

For \\(s^3 + 6s^2 + 11s + 6\\), the Routh array's first column is \\(1, 6, 10, 6\\) — all positive, so the system is stable (roots at \\(-1,-2,-3\\)).

## Root Locus

The **root locus** traces how the closed-loop poles move in the \\(s\\)-plane as a gain \\(K\\) varies from 0 to \\(\infty\\). Loci start at open-loop poles, end at open-loop zeros, and follow rules (real-axis segments, asymptotes, breakaway points) that let you sketch them by hand and pick \\(K\\) for a desired damping.

## Nyquist Criterion

The **Nyquist criterion** uses the open-loop frequency response \\(G(j\omega)H(j\omega)\\). Counting encirclements \\(N\\) of the critical point \\(-1\\):
\\[
Z = N + P,
\\]
where \\(P\\) is the number of open-loop right-half-plane poles and \\(Z\\) the closed-loop ones. \\(Z=0\\) means stable. Nyquist handles time delays and non-minimum-phase systems that Routh cannot.

## Stability Margins

From the Bode plot (see [Frequency Response](frequency.md)):

- **Gain margin (GM):** how much the gain can increase before instability — measured where phase \\(= -180^\circ\\).
- **Phase margin (PM):** extra phase lag tolerable before instability — measured where gain \\(= 0\\) dB.

Healthy designs target **GM > 6 dB** and **PM > 45°**. Small margins mean ringing and fragility to modeling error.

## See Also

- [Stability and Causality](../../signals/stability.md)
- [Frequency Response](frequency.md)
- [Transfer Functions](transfer.md)
