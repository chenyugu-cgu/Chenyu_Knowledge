# Second-Order Linear ODEs

Second-order linear ODEs model every oscillating system — springs, circuits, control loops — so they are the most important class in engineering.

## Homogeneous, Constant Coefficients

For \\(a y'' + b y' + c y = 0\\), try \\(y = e^{rx}\\) to get the **characteristic equation**
\\[
a r^2 + b r + c = 0.
\\]
The roots determine the solution:

| Roots | General solution |
|---|---|
| Real distinct \\(r_1, r_2\\) | \\(C_1 e^{r_1 x} + C_2 e^{r_2 x}\\) |
| Real repeated \\(r\\) | \\((C_1 + C_2 x)e^{r x}\\) |
| Complex \\(\alpha \pm i\beta\\) | \\(e^{\alpha x}(C_1\cos\beta x + C_2\sin\beta x)\\) |

These three cases correspond exactly to **overdamped, critically damped, and underdamped** systems — see [Vibrations](../../eng/dynamics/vibrations.md).

## Nonhomogeneous Equations

The general solution is \\(y = y_h + y_p\\), the homogeneous part plus any particular solution. Two methods find \\(y_p\\):

- **Undetermined coefficients** — guess a form matching the forcing (polynomial, exponential, sinusoid) and solve for coefficients. Fast when the forcing is simple.
- **Variation of parameters** — works for any forcing: \\(y_p = -y_1\!\int\frac{y_2 g}{W}dx + y_2\!\int\frac{y_1 g}{W}dx\\), with Wronskian \\(W\\).

## Resonance

Driving \\(y'' + \omega_n^2 y = F_0\cos\omega t\\) at \\(\omega = \omega_n\\) produces an unbounded, growing response (\\(y_p \propto t\sin\omega_n t\\)) — **resonance**. With damping the response is large but finite, peaking near \\(\omega_n\\). This is the mechanism behind tuned circuits and structural failures.

## Worked Example: Damped Oscillator

\\(y'' + 2y' + 5y = 0\\): roots \\(r = -1 \pm 2i\\), so
\\[
y = e^{-x}(C_1\cos 2x + C_2\sin 2x)
\\]
— a decaying oscillation (\\(\zeta = 1/\sqrt5\\), underdamped).

## See Also

- [Systems of ODEs](systems.md)
- [Laplace Transform Methods](laplace-method.md)
- [Vibrations](../../eng/dynamics/vibrations.md)
