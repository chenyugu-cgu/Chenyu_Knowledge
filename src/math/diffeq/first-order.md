# First-Order ODEs

A first-order ODE has the form \\(y' = f(x, y)\\). Several special structures admit closed-form solutions.

## Separable Equations

If the equation separates as \\(\dfrac{dy}{dx} = g(x)h(y)\\), integrate each side:
\\[
\int \frac{dy}{h(y)} = \int g(x)\,dx + C.
\\]

**Example.** \\(y' = ky\\) gives \\(y = y_0 e^{kx}\\) — exponential growth/decay (radioactive decay, RC discharge, population).

## Linear First-Order Equations

The standard form \\(y' + P(x)y = Q(x)\\) is solved with an **integrating factor** \\(\mu = e^{\int P\,dx}\\):
\\[
y = \frac{1}{\mu}\left(\int \mu\,Q\,dx + C\right).
\\]
Multiplying by \\(\mu\\) turns the left side into \\((\mu y)'\\), which integrates directly.

**Example.** \\(y' + 2y = e^{-x}\\): \\(\mu = e^{2x}\\), so \\((e^{2x}y)' = e^{x}\\), giving \\(y = e^{-x} + Ce^{-2x}\\).

## Exact Equations

\\(M\,dx + N\,dy = 0\\) is **exact** if \\(\partial M/\partial y = \partial N/\partial x\\); then there is a potential \\(F\\) with \\(dF = 0\\), so \\(F(x,y) = C\\). Non-exact equations can sometimes be made exact with an integrating factor.

## Existence and Uniqueness

The **Picard–Lindelöf theorem**: if \\(f\\) and \\(\partial f/\partial y\\) are continuous near \\((x_0, y_0)\\), a unique solution exists locally. This guarantees that a well-posed initial-value problem has exactly one solution.

## Applications

- **Growth/decay:** \\(\dot{N} = kN\\).
- **Newton's cooling:** \\(\dot{T} = -k(T - T_\infty)\\).
- **RC circuit:** \\(\tau\dot{v} + v = v_{in}\\) (time constant \\(\tau = RC\\)).
- **Logistic growth:** \\(\dot{P} = rP(1 - P/K)\\) (separable, gives the S-curve).

## See Also

- [Second-Order Linear ODEs](second-order.md)
- [Integration](../calculus/integration.md)
- [Time-Domain Analysis](../../signals/time-domain.md)
