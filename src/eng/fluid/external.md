# External Flows

External flows surround a body immersed in fluid — air over a wing, water past a hull, wind on a building. The central concerns are **drag**, **lift**, and the **boundary layer**.

## The Boundary Layer

Near a surface, viscosity forces the fluid to match the wall velocity (no-slip), creating a thin **boundary layer** where velocity rises from zero to the free-stream value. The layer starts laminar and may transition to turbulent. Its growth and separation govern drag and heat transfer. Outside it, the flow behaves as nearly inviscid.

## Drag

Total drag combines friction (viscous shear) and pressure (form) drag:
\\[
F_D = \tfrac{1}{2}\rho V^2 A\, C_D,
\\]
where \\(C_D\\) is the **drag coefficient** (a function of \\(Re\\) and shape) and \\(A\\) is a reference area. Streamlining reduces pressure drag by delaying boundary-layer separation; a sphere's \\(C_D\\) actually **drops** at high \\(Re\\) when the boundary layer turns turbulent (why golf balls have dimples).

## Lift

A body can also generate force perpendicular to the flow:
\\[
F_L = \tfrac{1}{2}\rho V^2 A\, C_L.
\\]
Lift arises from circulation and pressure differences (Kutta–Joukowski). An airfoil's \\(C_L\\) rises with angle of attack until **stall**, when the boundary layer separates and lift collapses.

## Flow Separation and Wakes

When the boundary layer can no longer follow an adverse pressure gradient, it **separates**, forming a low-pressure wake that dominates form drag. Bluff bodies (cylinders, cars) separate early; streamlined bodies keep flow attached.

## Vortex Shedding

Behind a bluff body, alternating vortices form a **von Kármán street** at a frequency set by the Strouhal number \\(St = f D/V \approx 0.2\\). This drives flow-induced vibration (singing wires, the original Tacoma Narrows mechanism).

## Terminal Velocity

A falling body reaches terminal velocity when drag balances weight:
\\[
V_t = \sqrt{\frac{2 m g}{\rho A C_D}}.
\\]

## See Also

- [Internal Flows](internal.md)
- [Turbulence](turbulence.md)
- [Aerodynamics in Robotics/Drones → Sensing and Perception](../../app/robotics/sensing.md)
