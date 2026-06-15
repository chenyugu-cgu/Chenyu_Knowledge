# System Properties

Before analyzing a system we classify it. These properties determine which mathematical tools apply and what behaviors to expect.

## Linearity

A system is **linear** if it satisfies superposition: scaling and summing inputs scales and sums outputs,
\\[
\mathcal{H}\{a x_1 + b x_2\} = a\,\mathcal{H}\{x_1\} + b\,\mathcal{H}\{x_2\}.
\\]
Linearity lets us decompose complex inputs into simple ones (impulses, sinusoids) and superpose the responses.

## Time Invariance

A system is **time-invariant** if its behavior does not change with time: \\(\mathcal{H}\{x(t-t_0)\} = y(t-t_0)\\). Combined with linearity this gives the **LTI** class, completely described by an impulse response.

## Causality

A system is **causal** if the output at time \\(t\\) depends only on present and past inputs, never future ones. For an LTI system this means \\(h(t) = 0\\) for \\(t < 0\\). All physically realizable real-time systems are causal; offline (recorded) processing may use non-causal filters.

## Memory

A system is **memoryless** (static) if the output at \\(t\\) depends only on the input at \\(t\\) (e.g. \\(y = 3x\\)). Otherwise it has **memory** (dynamic), as with integrators, delays, and any system with energy storage.

## Stability

A system is **BIBO stable** if every bounded input produces a bounded output. For LTI systems this is equivalent to an absolutely integrable/summable impulse response:
\\[
\int_{-\infty}^{\infty}|h(t)|\,dt < \infty
\quad\text{or}\quad
\sum_{n=-\infty}^{\infty}|h[n]| < \infty.
\\]
See [Stability and Causality](stability.md).

## Invertibility

A system is **invertible** if distinct inputs always produce distinct outputs, so that the input can be recovered. Cascading a system with its inverse yields the identity \\(\delta(t)\\).

## Summary Table

| Property | LTI test |
|---|---|
| Linear | superposition holds |
| Time-invariant | \\(h\\) independent of absolute time |
| Causal | \\(h(t)=0\\) for \\(t<0\\) |
| Memoryless | \\(h(t)=c\,\delta(t)\\) |
| Stable | \\(\int|h|\,dt<\infty\\) |
| Invertible | exists \\(h_{\text{inv}}\\) with \\(h * h_{\text{inv}}=\delta\\) |

## Example: Classifying \\(y[n] = x[n] + 2x[n-1]\\)

Linear (✓ superposition), time-invariant (✓ constant coefficients), causal (✓ uses only present/past), has memory (uses \\(n-1\\)), stable (FIR, finite \\(\sum|h|\\)). Its impulse response is \\(h[n]=\{1,2\}\\).

## See Also

- [Time-Domain Analysis](time-domain.md)
- [Stability and Causality](stability.md)
