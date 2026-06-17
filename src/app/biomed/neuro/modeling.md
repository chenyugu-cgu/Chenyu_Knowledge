# Computational Neural Modeling

Computational models predict how neurons behave and how stimulation recruits them — turning the [physiology](neurophysiology.md) and [stimulation physics](stimulation-theory.md) into equations you can simulate. Both recent spinal-stimulation papers rest on exactly the models below.

## The Hodgkin–Huxley Model

Hodgkin and Huxley (1952) modeled the membrane as a capacitor in parallel with voltage-gated conductances:
\\[
C_m\frac{dV}{dt} = -\bar{g}_{Na} m^3 h\,(V - E_{Na}) - \bar{g}_K n^4 (V - E_K) - g_L(V - E_L) + I_{stim},
\\]
where gating variables \\(m, h, n\\) follow first-order kinetics \\(\dot{x} = \alpha_x(V)(1-x) - \beta_x(V)x\\). This nonlinear [ODE system](../../../math/diffeq/systems.md) reproduces the action potential, threshold, and refractoriness, and is the ancestor of every conductance-based model.

## Cable Theory

A neurite is an electrical **cable**: membrane capacitance and resistance in parallel, axial resistance along the core. The **cable equation**:
\\[
\lambda^2\frac{\partial^2 V}{\partial x^2} = \tau_m\frac{\partial V}{\partial t} + V,
\\]
with space constant \\(\lambda = \sqrt{r_m/r_a}\\) and time constant \\(\tau_m = r_m c_m\\). The \\(\partial^2 V/\partial x^2\\) term is exactly what couples an external field to the membrane — the origin of the [activating function](stimulation-theory.md).

## Compartmental Models

To handle realistic geometry, an axon or neuron is split into connected **compartments**, each a Hodgkin–Huxley-style circuit, solved numerically (the NEURON simulator is standard). This is how dendrites, branch points, and myelinated structure are modeled.

## The Myelinated-Axon (MRG) Model

Stimulation studies use a **double-cable model of myelinated fibre** (McIntyre–Richardson–Grill, "MRG"). Each internode is resolved into compartments:

- **node** of Ranvier (active: fast & persistent Na⁺, slow K⁺, leak — \\(\text{Na}_f, \text{Na}_p, \text{K}_s, \text{Lk}\\));
- **MYSA** (paranodal myelin attachment segment);
- **FLUT** (paranodal main segment);
- **STIN** (internodal segments under myelin).

A double cable represents both the axolemma and the myelin sheath with the periaxonal space between. Fibre-diameter-dependent geometry makes the model reproduce real conduction velocities and **diameter-dependent thresholds** — which is why it predicts afferent-vs-efferent recruitment and the kHz-waveform effects of [stimulation theory](stimulation-theory.md). This is the "conductance-based cable model" in Keesey et al. (2026).

## Volume-Conductor (Field) Models

The other half is computing the extracellular potential \\(V_e\\) that the axon model needs. Tissue is a **volume conductor**; for quasi-static fields,
\\[
\nabla\cdot(\sigma\nabla V_e) = -I_{source},
\\]
a Poisson/Laplace equation (see [Electromagnetism](../../../physics/em/maxwell.md) and [PDEs](../../../math/diffeq/pdes.md)) solved by the **finite element method** ([FEM](../../../math/numerical/fem.md)) over an anatomically realistic 3-D mesh (skin, fat, bone, CSF, nerve — each with its conductivity \\(\sigma\\)). The computed \\(V_e\\) is then imposed on the MRG axons to predict recruitment.

## The Two-Step Recipe

\\[
\underbrace{\text{FEM field model}}_{V_e(\mathbf{x})} \;\longrightarrow\; \underbrace{\text{MRG axon model}}_{\text{threshold, AP}} \;\longrightarrow\; \text{recruitment curves}.
\\]
This pipeline — field model feeding fibre models — is the workhorse of modern neuromodulation research and the method behind both spinal-stimulation papers. It lets engineers test electrode placements and waveforms *in silico* before any experiment.

## See Also

- [Electrical Stimulation of Neural Tissue](stimulation-theory.md)
- [Systems of ODEs](../../../math/diffeq/systems.md), [Finite Element Methods](../../../math/numerical/fem.md)
- [Spinal Cord Stimulation and Neurorehabilitation](spinal-stimulation.md)
