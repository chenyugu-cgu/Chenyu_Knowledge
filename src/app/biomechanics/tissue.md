# Tissue Mechanics

Biological tissues are mechanically unlike engineering metals: they are soft, hydrated, anisotropic, and **viscoelastic**, and they adapt to load. Tissue mechanics models how bone, soft tissue, and cells deform and fail.

## Viscoelasticity

Tissues exhibit time-dependent behavior — their response depends on loading rate and history:
- **Creep** — slow deformation under constant load.
- **Stress relaxation** — declining stress under constant strain.
- **Hysteresis** — energy loss in load–unload cycles.

Modeled with spring–dashpot combinations (Maxwell, Kelvin–Voigt, standard linear solid):
\\[
\sigma + \tau_\sigma\dot{\sigma} = E(\varepsilon + \tau_\varepsilon\dot{\varepsilon}).
\\]
See [Joint Modeling](joints.md) for these models in context.

## Nonlinear, Anisotropic Behavior

Soft tissues (tendon, skin, artery) show a **J-shaped** stress–strain curve: a compliant "toe" region (crimped collagen straightening) stiffening sharply as fibers engage. They are **anisotropic** — much stiffer along fiber directions — and often modeled as fiber-reinforced **hyperelastic** materials (large reversible strains, strain-energy functions).

## Bone

Bone is a stiff composite (collagen + mineral). It is anisotropic and **remodels** in response to load (**Wolff's law**) — strengthening where stressed, resorbing where unloaded. This adaptation drives implant design to avoid [stress shielding](../biomed/biomaterials.md).

## Poroelasticity

Hydrated tissues like **cartilage** behave poroelastically: load squeezes interstitial fluid through the matrix, giving rate-dependent stiffness and lubrication. This biphasic behavior explains cartilage's load distribution and its degeneration in osteoarthritis.

## Failure and Injury

Tissues fail by tearing, fracture, or fatigue. Injury biomechanics studies thresholds (ligament rupture, bone fracture, concussion) to design protective equipment and predict [injury](ergonomics.md). Rate sensitivity matters: bone is stronger but more brittle at high loading rates.

## See Also

- [Joint Modeling](joints.md)
- [Elasticity](../../eng/materials/elasticity.md)
- [Biomaterials](../biomed/biomaterials.md)
