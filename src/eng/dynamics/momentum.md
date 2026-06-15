# Impulse and Momentum

The impulse–momentum method integrates Newton's law over **time**. It is the natural tool for impacts, collisions, jets, and any problem where forces act briefly or where masses interact.

## Linear Impulse and Momentum

The **linear momentum** of a particle is \\(\mathbf{p} = m\mathbf{v}\\). Integrating \\(\sum \mathbf{F} = d\mathbf{p}/dt\\) over time gives the **impulse–momentum theorem**:
\\[
\int_{t_1}^{t_2}\sum \mathbf{F}\,dt = \mathbf{p}_2 - \mathbf{p}_1 = m\mathbf{v}_2 - m\mathbf{v}_1.
\\]
The integral on the left is the **impulse** — the area under the force–time curve.

## Conservation of Momentum

If the net external impulse is zero (e.g. an isolated collision), total momentum is conserved:
\\[
\sum m_i \mathbf{v}_i \big|_{\text{before}} = \sum m_i \mathbf{v}_i \big|_{\text{after}}.
\\]
This holds even when large, unknown internal forces act during the impact.

## Collisions and the Coefficient of Restitution

For a direct central impact between bodies \\(A\\) and \\(B\\), the **coefficient of restitution** \\(e\\) relates relative velocities along the line of impact:
\\[
e = \frac{v_B' - v_A'}{v_A - v_B}, \qquad 0 \le e \le 1.
\\]
- \\(e=1\\): **perfectly elastic** (kinetic energy conserved).
- \\(e=0\\): **perfectly plastic** (bodies stick together).

Combined with momentum conservation, \\(e\\) determines both post-impact velocities.

## Angular Momentum

About a point \\(O\\), the angular momentum is \\(\mathbf{H}_O = \mathbf{r}\times m\mathbf{v}\\) (or \\(I_O\omega\\) for a rigid body). The angular impulse–momentum principle is
\\[
\int_{t_1}^{t_2}\sum M_O\,dt = (H_O)_2 - (H_O)_1.
\\]
With no external moment, **angular momentum is conserved** — why a spinning skater speeds up when pulling in their arms (\\(I\downarrow \Rightarrow \omega\uparrow\\)).

## Worked Example: Perfectly Plastic Collision

A mass \\(m_1\\) at speed \\(v\\) strikes a stationary \\(m_2\\) and they move off together:
\\[
v' = \frac{m_1 v}{m_1 + m_2}, \qquad
\frac{T_{\text{after}}}{T_{\text{before}}} = \frac{m_1}{m_1 + m_2}.
\\]
The kinetic-energy loss (the missing fraction) goes into deformation and heat.

## Variable-Mass Systems

For rockets, the thrust arises from ejecting mass at relative speed \\(u\\), giving the Tsiolkovsky rocket equation \\(\Delta v = u\ln(m_0/m_f)\\).

## See Also

- [Newton's Laws](newton.md)
- [Work and Energy](energy.md)
