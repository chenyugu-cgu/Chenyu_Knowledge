# Formula Reference

A condensed index of the key formulas in this book, grouped by domain, with links to the chapters that derive them.

## Calculus and Linear Algebra

- Derivative (limit): \\(f'(x) = \lim_{h\to0}\frac{f(x+h)-f(x)}{h}\\) — [Differentiation](../math/calculus/differentiation.md)
- Fundamental theorem: \\(\int_a^b f'(x)\,dx = f(b)-f(a)\\) — [Integration](../math/calculus/integration.md)
- Taylor series: \\(f(x)=\sum_n \frac{f^{(n)}(a)}{n!}(x-a)^n\\) — [Series and Sequences](../math/calculus/series.md)
- Eigenvalue problem: \\(A\mathbf{v}=\lambda\mathbf{v}\\) — [Eigenvalues](../math/linear-algebra/eigen.md)
- SVD: \\(A = U\Sigma V^T\\) — [Singular Value Decomposition](../math/linear-algebra/svd.md)

## Probability and Statistics

- Bayes: \\(P(A\mid B)=\dfrac{P(B\mid A)P(A)}{P(B)}\\) — [Bayesian Inference](../math/probability/bayes.md)
- Expectation/variance: \\(\mathbb{E}[X]=\sum x p(x)\\), \\(\operatorname{Var}(X)=\mathbb{E}[X^2]-\mathbb{E}[X]^2\\) — [Expectation](../math/probability/expectation.md)
- CLT: \\(\bar{X}_n \approx \mathcal{N}(\mu, \sigma^2/n)\\) — [LLN & CLT](../math/probability/clt.md)

## Signals and Systems

- Convolution: \\(y(t)=\int x(\tau)h(t-\tau)\,d\tau\\) — [Convolution](../signals/convolution.md)
- Fourier transform: \\(X(\omega)=\int x(t)e^{-j\omega t}\,dt\\) — [Fourier Transform](../signals/fourier-transform.md)
- Laplace transform: \\(X(s)=\int_{0^-}^{\infty} x(t)e^{-st}\,dt\\) — [Laplace Transform](../signals/laplace-transform.md)
- Nyquist rate: \\(f_s > 2 f_{\max}\\) — [Sampling](../signals/sampling.md)

## Mechanics

- Equilibrium: \\(\sum\mathbf{F}=0,\ \sum\mathbf{M}=0\\) — [Equilibrium](../eng/statics/equilibrium.md)
- Newton: \\(\sum\mathbf{F}=m\mathbf{a}\\) — [Newton's Laws](../eng/dynamics/newton.md)
- Work–energy: \\(U_{1\to2}=\Delta T\\) — [Work and Energy](../eng/dynamics/energy.md)
- Impulse–momentum: \\(\int\mathbf{F}\,dt=\Delta\mathbf{p}\\) — [Momentum](../eng/dynamics/momentum.md)
- Axial: \\(\sigma=N/A,\ \delta=NL/AE\\) — [Axial Loading](../eng/materials/axial.md)
- Bending: \\(\sigma=My/I\\) — [Bending and Shear](../eng/materials/bending.md)
- Torsion: \\(\tau=Tr/J,\ \phi=TL/JG\\) — [Torsion](../eng/materials/torsion.md)
- Euler buckling: \\(P_{cr}=\pi^2EI/(KL)^2\\) — [Failure Theories](../eng/materials/failure.md)
- Natural frequency: \\(\omega_n=\sqrt{k/m}\\) — [Vibrations](../eng/dynamics/vibrations.md)

## Thermofluids

- First law: \\(\Delta U = Q - W\\) — [Laws of Thermodynamics](../eng/thermo/laws.md)
- Carnot efficiency: \\(\eta = 1 - T_C/T_H\\) — [Power Cycles](../eng/thermo/cycles.md)
- Bernoulli: \\(p + \tfrac12\rho V^2 + \rho g z = \text{const}\\) — [Conservation Laws](../eng/fluid/conservation.md)
- Reynolds number: \\(Re = \rho V L/\mu\\) — [Internal Flows](../eng/fluid/internal.md)
- Darcy–Weisbach: \\(h_f = f\,(L/D)\,V^2/2g\\) — [Internal Flows](../eng/fluid/internal.md)

## Electrical and Control

- Ohm: \\(V = IR\\), power \\(P=VI\\) — [Circuit Laws](../eng/electrical/circuits.md)
- Impedance: \\(Z_L=j\omega L,\ Z_C=1/j\omega C\\) — [AC and DC Analysis](../eng/electrical/ac-dc.md)
- Closed loop: \\(T=\dfrac{CG}{1+CG}\\) — [Control Systems](../eng/control/README.md)
- PID: \\(u=K_pe+K_i\!\int e+K_d\dot e\\) — [PID Control](../eng/control/pid.md)
- LQR gain: \\(K=R^{-1}B^TP\\) — [Optimal Control](../eng/control/optimal.md)

## Machine Learning and Optimization

- Empirical risk: \\(\min_\theta \frac1n\sum\ell(f_\theta(x_i),y_i)+\lambda\Omega(\theta)\\) — [Supervised Learning](../cs/ml/supervised.md)
- Gradient step: \\(\mathbf{x}_{k+1}=\mathbf{x}_k-\alpha\nabla f\\) — [Gradient Descent](../cs/optimization/gradient.md)
- Ridge: \\(\hat\theta=(X^TX+\lambda I)^{-1}X^Ty\\) — [Regularization](../cs/ml/regularization.md)
- KKT stationarity: \\(\nabla f+\sum\mu_i\nabla g_i+\sum\lambda_j\nabla h_j=0\\) — [Constrained Optimization](../cs/optimization/constrained.md)

## See Also

- [Mathematical Tables](tables.md)
- [Notation Index](notation.md)
