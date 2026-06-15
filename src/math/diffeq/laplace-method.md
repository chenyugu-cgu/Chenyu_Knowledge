# Laplace Transform Methods

The Laplace transform turns a linear ODE with initial conditions into an **algebraic** equation, solves it, and inverts back to the time domain. It is the cleanest route for forced systems with discontinuous or impulsive inputs.

## The Procedure

1. **Transform** the ODE term-by-term, using
\\[
\mathcal{L}\{y'\} = sY(s) - y(0), \qquad \mathcal{L}\{y''\} = s^2 Y(s) - s y(0) - y'(0).
\\]
Initial conditions fold in automatically.
2. **Solve** the algebraic equation for \\(Y(s)\\).
3. **Invert** \\(Y(s)\\) — usually by partial fractions and a table of transform pairs.

See the [Laplace Transform](../../signals/laplace-transform.md) chapter for the transform itself and a table of pairs.

## Worked Example

Solve \\(y'' + 3y' + 2y = 0\\), \\(y(0)=1\\), \\(y'(0)=0\\).

Transforming: \\((s^2 + 3s + 2)Y - s - 3 = 0\\), so
\\[
Y(s) = \frac{s+3}{(s+1)(s+2)} = \frac{2}{s+1} - \frac{1}{s+2}
\quad\Rightarrow\quad y(t) = 2e^{-t} - e^{-2t}.
\\]

## Handling Special Inputs

- **Step input** \\(u(t)\\): transform \\(1/s\\) — models switching on a source.
- **Impulse** \\(\delta(t)\\): transform \\(1\\) — models a sharp kick (the response is the impulse response \\(h(t)\\)).
- **Time-shifted inputs** \\(f(t-a)u(t-a)\\): transform \\(e^{-as}F(s)\\) — handles piecewise forcing cleanly.

## Why Engineers Love It

- Initial conditions are built in (no separate constant-fitting).
- Discontinuous and impulsive forcing are routine.
- The transfer function \\(H(s) = Y(s)/U(s)\\) drops out directly, linking to [control](../../eng/control/transfer.md) and [signals](../../signals/laplace-transform.md).

## See Also

- [Laplace Transform](../../signals/laplace-transform.md)
- [Transfer Functions](../../eng/control/transfer.md)
- [Second-Order Linear ODEs](second-order.md)
