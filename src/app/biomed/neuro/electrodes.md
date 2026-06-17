# Neural Interfaces and Electrodes

The electrode is where electronics meets neurons. Its job is to convert between the **electronic** currents of a device and the **ionic** currents of tissue — for both recording and stimulation — safely and for years. Electrode design largely determines what a neural interface can do.

## The Electrode–Tissue Interface

At the metal–electrolyte boundary, charge crosses by two mechanisms:

- **Capacitive (non-Faradaic)** — charging/discharging the double-layer; no chemical reaction, fully reversible, safest.
- **Faradaic** — electron transfer via redox reactions; reversible reactions (e.g. iridium oxide valence changes) are usable, irreversible ones (electrolysis, corrosion) damage tissue and electrode.

The interface is modeled as a **double-layer capacitance** in parallel with a Faradaic resistance, in series with the solution resistance — giving the electrode its frequency-dependent **impedance**.

## Safe Charge Injection

Stimulation must stay within reversible limits. Damage risk rises with both charge per phase and charge **density**; the empirical **Shannon criterion**:
\\[
\log\!\left(\frac{Q}{A}\right) = k - \log(Q),
\\]
relates charge density \\(Q/A\\) and charge \\(Q\\) per phase, with \\(k \approx 1.5\text{–}2.0\\) bounding the safe region. **Biphasic, charge-balanced** pulses ([stimulation theory](stimulation-theory.md)) keep the interface reversible. Smaller electrodes give finer selectivity but hit charge-density limits sooner — the central design tension.

## Electrode Materials

| Material | Use | Note |
|---|---|---|
| Platinum / Pt-Ir | clinical stimulation | robust, moderate charge capacity |
| Iridium oxide (IrOx) | high charge injection | reversible Faradaic |
| TiN | capacitive | high surface area |
| PEDOT:PSS | low impedance | conductive polymer coating |
| Carbon / graphene | research | flexible, MRI-compatible |

Coatings increase effective surface area, lowering impedance and raising safe charge injection.

## Electrode Technologies

Matched to the target scale and acceptable invasiveness:

| Interface | Signal scale | Example |
|---|---|---|
| Scalp (EEG) | populations | non-invasive |
| Epidural / subdural (ECoG) | local populations | surface grids |
| Penetrating arrays | single units | Utah array, Michigan probes |
| Microwires / cones | single units | neurotrophic electrode |
| Nerve cuffs / LIFE | peripheral nerve | FES, sensory feedback |
| Paddle / percutaneous leads | spinal roots | [spinal cord stimulation](spinal-stimulation.md) |
| Surface (transcutaneous) | non-invasive | tSCS, surface FES |

The Utah array (~100 silicon needles) records cortical single units for [BCIs](bci.md); paddle leads over the dorsal spinal cord target posterior roots for [neurorehabilitation](spinal-stimulation.md).

## Biocompatibility and Longevity

Implants trigger a **foreign-body response**: inflammation and glial scar (encapsulation) that raises impedance and degrades recording over months. Mitigations include flexible/soft substrates that match tissue mechanics (see [Biomaterials](../biomaterials.md)), small cross-sections, and anti-inflammatory coatings. Chronic stability is the field's hardest unsolved problem.

## See Also

- [Electrical Stimulation of Neural Tissue](stimulation-theory.md)
- [Neural Recording and Decoding](recording-decoding.md)
- [Biomaterials](../biomaterials.md), [Bioinstrumentation](../instrumentation.md)
