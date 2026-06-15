# Bioinstrumentation

Bioinstrumentation designs the devices that **measure** physiological quantities and **deliver** therapy — from ECG monitors to infusion pumps. It applies [mechatronics](../../eng/mechatronics/README.md) and [signal conditioning](../../eng/mechatronics/interfacing.md) under stringent safety constraints.

## The Measurement Chain

\\[
\text{biological signal} \to \text{transducer} \to \text{amplify + filter} \to \text{ADC} \to \text{process/display}.
\\]
Each stage mirrors general [instrumentation](../../eng/mechatronics/interfacing.md), with biology-specific challenges: tiny signals, large interference, and a living, moving subject.

## Biopotential Electrodes

Recording ECG/EEG/EMG requires electrodes that transduce **ionic** body currents to **electronic** currents. The skin–electrode interface adds impedance, offset (half-cell) potentials, and motion artifact. **Ag/AgCl** electrodes minimize drift; dry and capacitive electrodes enable wearables.

## Amplifiers and Noise

Biopotentials (µV–mV) ride on much larger interference (50/60 Hz powerline, motion). The **instrumentation amplifier** provides high gain with very high **common-mode rejection ratio (CMRR)**, and a **driven-right-leg** circuit actively cancels common-mode noise. Careful grounding and shielding are essential (see [Interfacing](../../eng/mechatronics/interfacing.md)).

## Patient Safety and Isolation

Because devices connect electrically to patients, **electrical isolation** (optical/transformer) prevents dangerous leakage currents to the heart — leakage limits are tens of microamps. Standards (IEC 60601) govern safety, and devices use redundancy, alarms, and fail-safe design.

## Common Instruments

| Instrument | Measures / does |
|---|---|
| ECG / EEG / EMG | biopotentials |
| Pulse oximeter | blood O₂ (optical absorption) |
| Blood-pressure monitor | arterial pressure |
| Infusion pump | controlled drug delivery |
| Ventilator | assisted breathing |

## Sensors and Biosensors

Beyond electrodes: pressure, temperature, flow, and **biosensors** that detect specific molecules (glucose meters use an enzyme-electrode [electrochemical](../../physics/chemistry/physical.md) reaction). Miniaturization enables implantable and wearable monitoring.

## See Also

- [Interfacing and Signal Conditioning](../../eng/mechatronics/interfacing.md)
- [Biosignal Processing](biosignals.md)
- [Sensors](../../eng/mechatronics/sensors.md)
