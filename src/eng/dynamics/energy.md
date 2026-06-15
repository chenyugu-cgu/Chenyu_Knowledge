# Work and Energy

The work–energy method integrates Newton's law over **distance**, relating force to changes in speed. It sidesteps acceleration and time, making it the fastest route to "how fast is it going *here*?" problems.

## Work

The work done by a force along a path is
\\[
U_{1\to2} = \int_{\mathbf{r}_1}^{\mathbf{r}_2} \mathbf{F}\cdot d\mathbf{r}.
\\]
Only the force component along the displacement does work. A constant force does \\(U = F d\cos\theta\\); a spring of stiffness \\(k\\) does \\(U = -\tfrac{1}{2}k(x_2^2 - x_1^2)\\) on the mass.

## Kinetic Energy and the Work–Energy Principle

\\[
T = \tfrac{1}{2}m v^2 \quad(\text{translation}), \qquad T = \tfrac{1}{2}I\omega^2 \quad(\text{rotation}).
\\]
The principle: the net work equals the change in kinetic energy,
\\[
U_{1\to2}^{\text{net}} = T_2 - T_1.
\\]

## Potential Energy and Conservation

For **conservative** forces, work is stored as potential energy:
\\[
V_g = m g h \ (\text{gravity}), \qquad V_e = \tfrac{1}{2}k x^2 \ (\text{spring}).
\\]
When only conservative forces act, total mechanical energy is conserved:
\\[
T_1 + V_1 = T_2 + V_2.
\\]
Non-conservative forces (friction, drag) are added as work terms: \\(T_1 + V_1 + U_{\text{nc}} = T_2 + V_2\\).

## Power and Efficiency

Power is the rate of doing work,
\\[
P = \frac{dU}{dt} = \mathbf{F}\cdot\mathbf{v} = M\omega,
\\]
and mechanical efficiency is \\(\eta = P_{\text{out}}/P_{\text{in}} \le 1\\).

## Worked Example: Roller Coaster

A car of mass \\(m\\) starts from rest at height \\(h\\) on a frictionless track. Its speed at the bottom follows from energy conservation:
\\[
mgh = \tfrac{1}{2}m v^2 \ \Rightarrow\ v = \sqrt{2gh},
\\]
independent of the track shape — the power of the energy method.

## Rolling Bodies

A body rolling without slipping has both translational and rotational kinetic energy. For a cylinder released on an incline of angle \\(\theta\\), energy methods give acceleration
\\[
a = \frac{g\sin\theta}{1 + I_G/(m r^2)},
\\]
so a hoop (\\(I=mr^2\\)) rolls slower than a solid cylinder (\\(I=\tfrac12 mr^2\\)) — the classic "race down the ramp."

## See Also

- [Newton's Laws](newton.md)
- [Impulse and Momentum](momentum.md)
- [Vibrations](vibrations.md)
