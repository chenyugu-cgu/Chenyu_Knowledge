# Biofluid Mechanics and Hemodynamics

Biofluid mechanics applies [fluid mechanics](../../eng/fluid/README.md) to the body's flows — blood, air, lymph, and fluids in medical devices. **Hemodynamics**, the study of blood flow, is its most developed branch.

## Blood as a Fluid

Blood is a **non-Newtonian** suspension of cells in plasma: its apparent viscosity decreases at higher shear rate (shear-thinning) and rises at low shear. In large vessels it behaves nearly Newtonian; in small vessels cell effects (the Fåhræus–Lindqvist effect) matter.

## Flow in Vessels

In a vessel, laminar flow approximates **Poiseuille flow**, where flow rate scales with the fourth power of radius:
\\[
Q = \frac{\pi r^4 \Delta p}{8\mu L}.
\\]
This dramatic \\(r^4\\) dependence means small changes in vessel diameter (vasoconstriction, stenosis) hugely affect flow and pressure — central to cardiovascular physiology. See [Internal Flows](../../eng/fluid/internal.md).

## Pulsatile Flow and Pressure Waves

Blood flow is **pulsatile**, driven by the beating heart. The **Windkessel model** captures arterial compliance and resistance as a circuit (compliance + resistance), predicting the diastolic pressure decay. Pressure and flow waves propagate and reflect along the arterial tree.

## The Reynolds Number in the Body

Flow is mostly laminar (\\(Re < 2000\\)), but turbulence appears at heart valves, in the aorta during peak ejection, and downstream of stenoses — audible as **murmurs/bruits**. Turbulence raises energy loss and shear stress.

## Wall Shear Stress and Disease

Endothelial cells sense **wall shear stress**; abnormal patterns (low/oscillatory shear at bends and bifurcations) promote **atherosclerosis**. Computational fluid dynamics ([CFD](../../eng/fluid/turbulence.md)) of patient-specific geometries predicts these risk regions.

## Measurement and Devices

[Doppler ultrasound](../../physics/optics/acoustics.md) measures blood velocity; the same fluid principles design heart valves, stents, vascular grafts, blood pumps (LVADs), and oxygenators — where hemolysis (shear damage to cells) is a key constraint.

## See Also

- [Internal Flows](../../eng/fluid/internal.md)
- [Conservation Laws](../../eng/fluid/conservation.md)
- [Physiological Systems Modeling](physiology.md)
