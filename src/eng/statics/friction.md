# Friction

Friction is the tangential resistance to relative sliding between contacting surfaces. In statics we deal mostly with **dry (Coulomb) friction**, which is what holds ladders against walls, lets belts drive pulleys, and makes wedges grip.

## Coulomb's Law of Dry Friction

The friction force \\(f\\) opposes impending or actual motion and satisfies
\\[
f \le \mu_s N \quad\text{(static)},\qquad f = \mu_k N \quad\text{(kinetic)},
\\]
where \\(N\\) is the normal force, \\(\mu_s\\) the **coefficient of static friction**, and \\(\mu_k < \mu_s\\) the kinetic coefficient. At the verge of slipping (**impending motion**) the inequality becomes an equality, \\(f = \mu_s N\\).

## Angle of Friction

The total contact reaction makes an angle \\(\phi\\) with the surface normal where
\\[
\tan\phi_s = \mu_s.
\\]
\\(\phi_s\\) is the **angle of static friction**. A block on an incline begins to slide when the incline angle reaches \\(\phi_s\\), giving the classic experiment \\(\mu_s = \tan\theta_{\text{slip}}\\).

## Problem-Solving Strategy

1. Draw the FBD with friction opposing impending motion.
2. Decide whether motion is **impending** (use \\(f=\mu_s N\\)) or the body is in equilibrium with a **range** of possible \\(f\\).
3. Solve equilibrium; verify \\(f \le \mu_s N\\) if you assumed equilibrium.

## Wedges

A wedge converts a small driving force into a large normal force for lifting or fixing. Analyze each contact surface with its friction angle; self-locking (the wedge stays put when the force is removed) occurs when the wedge angle is below \\(2\phi_s\\).

## Belt Friction (Capstan Equation)

For a belt or rope wrapping a drum through contact angle \\(\beta\\) (radians), the tensions on the two sides at impending slip obey
\\[
\frac{T_{\text{tight}}}{T_{\text{slack}}} = e^{\mu \beta}.
\\]
The exponential explains why a few turns around a capstan let a sailor hold an enormous load: with \\(\mu=0.3\\) and three wraps (\\(\beta=6\pi\\)), the ratio exceeds 300.

## Worked Example: Block on an Incline

A block of weight \\(W\\) rests on a \\(\theta\\) incline. Resolving along/normal to the surface:
\\[
N = W\cos\theta, \qquad f_{\text{required}} = W\sin\theta.
\\]
It stays put while \\(W\sin\theta \le \mu_s W\cos\theta\\), i.e. \\(\tan\theta \le \mu_s\\). Slip impends exactly at \\(\theta = \arctan\mu_s\\).

## See Also

- [Forces and Equilibrium](equilibrium.md)
- [Newton's Laws](../dynamics/newton.md) — friction once motion begins.
