# Laplace Transform

The Laplace transform extends the Fourier transform to a complex frequency variable \\(s = \sigma + j\omega\\). It handles signals that grow or are not absolutely integrable, converts linear differential equations into algebraic equations, and is the foundation of classical control theory.

## Definition

The (unilateral) Laplace transform is
\\[
X(s) = \mathcal{L}\{x(t)\} = \int_{0^-}^{\infty} x(t)\, e^{-st}\, dt,
\\]
defined on a **region of convergence (ROC)** \\(\operatorname{Re}(s) > \sigma_0\\) where the integral exists. The bilateral transform integrates from \\(-\infty\\); for causal signals the two agree.

## Key Properties

| Property | \\(x(t)\\) | \\(X(s)\\) |
|---|---|---|
| Linearity | \\(a x_1 + b x_2\\) | \\(a X_1 + b X_2\\) |
| Time shift | \\(x(t-t_0)u(t-t_0)\\) | \\(e^{-st_0}X(s)\\) |
| Differentiation | \\(x'(t)\\) | \\(sX(s) - x(0^-)\\) |
| Integration | \\(\int_0^t x\,d\tau\\) | \\(X(s)/s\\) |
| Convolution | \\(x*h\\) | \\(X(s)H(s)\\) |
| Frequency shift | \\(e^{-at}x(t)\\) | \\(X(s+a)\\) |

The differentiation property — folding in initial conditions — is what lets us solve initial-value problems algebraically.

## Common Transform Pairs

\\[
\delta(t)\leftrightarrow 1,\quad
u(t)\leftrightarrow \frac{1}{s},\quad
e^{-at}u(t)\leftrightarrow \frac{1}{s+a},\quad
\sin(\omega t)u(t)\leftrightarrow \frac{\omega}{s^2+\omega^2}.
\\]

## Transfer Functions, Poles and Zeros

For an LTI system, the **transfer function** is \\(H(s) = Y(s)/X(s)\\), a ratio of polynomials
\\[
H(s) = \frac{b_m s^m + \cdots + b_0}{a_n s^n + \cdots + a_0}.
\\]
The roots of the numerator are **zeros**; the roots of the denominator are **poles**. Pole locations determine the system's natural modes \\(e^{p_i t}\\): poles in the left half-plane decay (stable), poles in the right half-plane grow (unstable).

## Initial- and Final-Value Theorems

\\[
x(0^+) = \lim_{s\to\infty} sX(s),
\qquad
\lim_{t\to\infty} x(t) = \lim_{s\to 0} sX(s)
\\]
(the latter valid only when all poles of \\(sX(s)\\) lie in the open left half-plane).

## Worked Example: Solving an ODE

Solve \\(\dot{y} + 3y = u(t)\\), \\(y(0)=0\\). Transforming: \\(sY + 3Y = 1/s\\), so
\\[
Y(s) = \frac{1}{s(s+3)} = \frac{1/3}{s} - \frac{1/3}{s+3}
\quad\Rightarrow\quad
y(t) = \tfrac{1}{3}\big(1 - e^{-3t}\big)u(t).
\\]
Partial-fraction expansion plus a table of pairs turns calculus into algebra.

## See Also

- [Z-Transform](z-transform.md) — the discrete-time analogue.
- [Transfer Functions](../eng/control/transfer.md) and [Stability Analysis](../eng/control/stability.md) in Control Systems.
