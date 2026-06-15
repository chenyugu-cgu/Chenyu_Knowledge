# Mathematical Tables

Quick-reference tables for the operations used throughout this book.

## Common Derivatives

| \\(f(x)\\) | \\(f'(x)\\) |
|---|---|
| \\(x^n\\) | \\(n x^{n-1}\\) |
| \\(e^{x}\\) | \\(e^{x}\\) |
| \\(a^{x}\\) | \\(a^{x}\ln a\\) |
| \\(\ln x\\) | \\(1/x\\) |
| \\(\sin x\\) | \\(\cos x\\) |
| \\(\cos x\\) | \\(-\sin x\\) |
| \\(\tan x\\) | \\(\sec^2 x\\) |
| \\(\arcsin x\\) | \\(1/\sqrt{1-x^2}\\) |
| \\(\arctan x\\) | \\(1/(1+x^2)\\) |

## Common Integrals (constants of integration omitted)

| \\(\int f(x)\,dx\\) | result |
|---|---|
| \\(x^n\ (n\neq-1)\\) | \\(x^{n+1}/(n+1)\\) |
| \\(1/x\\) | \\(\ln\lvert x\rvert\\) |
| \\(e^{x}\\) | \\(e^{x}\\) |
| \\(\sin x\\) | \\(-\cos x\\) |
| \\(\cos x\\) | \\(\sin x\\) |
| \\(\sec^2 x\\) | \\(\tan x\\) |
| \\(1/(1+x^2)\\) | \\(\arctan x\\) |
| \\(1/\sqrt{1-x^2}\\) | \\(\arcsin x\\) |

## Trigonometric Identities

\\[
\sin^2\theta + \cos^2\theta = 1, \qquad 1 + \tan^2\theta = \sec^2\theta.
\\]
\\[
\sin(a\pm b) = \sin a\cos b \pm \cos a\sin b, \qquad
\cos(a\pm b) = \cos a\cos b \mp \sin a\sin b.
\\]
\\[
\sin 2\theta = 2\sin\theta\cos\theta, \qquad
\cos 2\theta = \cos^2\theta - \sin^2\theta = 1 - 2\sin^2\theta.
\\]
Euler: \\(e^{j\theta} = \cos\theta + j\sin\theta\\).

## Series Expansions (about \\(x=0\\))

\\[
e^{x} = \sum_{n=0}^{\infty}\frac{x^n}{n!}, \qquad
\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \cdots, \qquad
\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \cdots,
\\]
\\[
\ln(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \cdots\ (|x|<1), \qquad
(1+x)^\alpha = \sum_{k=0}^{\infty}\binom{\alpha}{k}x^k.
\\]

## Laplace Transform Pairs

| \\(f(t)\\) | \\(F(s)\\) |
|---|---|
| \\(\delta(t)\\) | \\(1\\) |
| \\(u(t)\\) | \\(1/s\\) |
| \\(t^n u(t)\\) | \\(n!/s^{n+1}\\) |
| \\(e^{-at}u(t)\\) | \\(1/(s+a)\\) |
| \\(\sin(\omega t)u(t)\\) | \\(\omega/(s^2+\omega^2)\\) |
| \\(\cos(\omega t)u(t)\\) | \\(s/(s^2+\omega^2)\\) |

## Fourier Transform Pairs

| \\(x(t)\\) | \\(X(\omega)\\) |
|---|---|
| \\(\delta(t)\\) | \\(1\\) |
| \\(1\\) | \\(2\pi\delta(\omega)\\) |
| \\(e^{-at}u(t)\\) | \\(1/(a+j\omega)\\) |
| \\(\operatorname{rect}(t/T)\\) | \\(T\operatorname{sinc}(\omega T/2\pi)\\) |
| \\(\cos(\omega_0 t)\\) | \\(\pi[\delta(\omega-\omega_0)+\delta(\omega+\omega_0)]\\) |

## See Also

- [Formula Reference](formulas.md)
- [Notation Index](notation.md)
- [Differentiation](../math/calculus/differentiation.md), [Integration](../math/calculus/integration.md)
