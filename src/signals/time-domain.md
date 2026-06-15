# Time-Domain Analysis

Time-domain analysis describes how a system responds to inputs directly as functions of time, without transforming into the frequency domain. For **linear time-invariant (LTI)** systems, the entire input–output behavior is captured by a single function: the impulse response.

## Linear Time-Invariant Systems

A system \\(\mathcal{H}\\) mapping \\(x(t)\mapsto y(t)\\) is **linear** if it obeys superposition,
\\[
\mathcal{H}\{a x_1 + b x_2\} = a\,\mathcal{H}\{x_1\} + b\,\mathcal{H}\{x_2\},
\\]
and **time-invariant** if a shift in input produces only an equal shift in output: \\(\mathcal{H}\{x(t-t_0)\} = y(t - t_0)\\). LTI systems are the backbone of signal processing because they are completely characterized by their response to an impulse.

## Impulse Response and Convolution

The **impulse response** \\(h(t)\\) is the output when the input is \\(\delta(t)\\). Because any input can be written as a continuum of shifted, scaled impulses,
\\[
x(t) = \int_{-\infty}^{\infty} x(\tau)\,\delta(t-\tau)\,d\tau,
\\]
linearity and time invariance give the **convolution integral**:
\\[
y(t) = (x * h)(t) = \int_{-\infty}^{\infty} x(\tau)\,h(t-\tau)\,d\tau.
\\]
In discrete time, \\(y[n] = \sum_{k=-\infty}^{\infty} x[k]\,h[n-k]\\). The chapter [Convolution and Correlation](convolution.md) treats this operation in depth.

## Step and Ramp Response

The **step response** \\(s(t)\\) is the output for input \\(u(t)\\). Since \\(u(t)=\int_{-\infty}^t \delta(\tau)d\tau\\), the step and impulse responses are related by integration/differentiation:
\\[
s(t) = \int_{-\infty}^{t} h(\tau)\, d\tau, \qquad h(t) = \frac{d}{dt}\,s(t).
\\]
Engineers often read off rise time, settling time, overshoot, and steady-state value directly from the step response.

## Systems Described by Differential Equations

Many physical LTI systems obey a linear constant-coefficient differential equation:
\\[
\sum_{k=0}^{N} a_k \frac{d^k y}{dt^k} = \sum_{m=0}^{M} b_m \frac{d^m x}{dt^m}.
\\]
The total solution is the sum of the **homogeneous** (natural) response, governed by the characteristic equation \\(\sum_k a_k s^k = 0\\), and a **particular** (forced) response that matches the input. Initial conditions fix the arbitrary constants.

### Example: First-Order RC Circuit

For an RC low-pass filter with time constant \\(\tau = RC\\),
\\[
\tau \dot{y}(t) + y(t) = x(t).
\\]
Its impulse response is \\(h(t) = \tfrac{1}{\tau} e^{-t/\tau} u(t)\\) and its step response is \\(s(t) = (1 - e^{-t/\tau})\,u(t)\\), rising to within 2% of final value after about \\(4\tau\\).

## Characterizing System Behavior

| Quantity | Meaning |
|---|---|
| Rise time \\(t_r\\) | Time to go 10% → 90% of final value |
| Settling time \\(t_s\\) | Time to stay within a tolerance band (e.g. 2%) |
| Overshoot \\(M_p\\) | Peak excess over steady state |
| Steady-state value | \\(\lim_{t\to\infty} y(t)\\) for a bounded input |

## See Also

- [Convolution and Correlation](convolution.md)
- [System Properties](system-properties.md)
- [Laplace Transform](laplace-transform.md) — the algebraic counterpart of these differential equations.
