# Sensors

A **sensor** converts a physical quantity into a measurable (usually electrical) signal. Choosing and characterizing sensors is the front end of every mechatronic and instrumentation system.

## Sensor Characteristics

| Property | Meaning |
|---|---|
| Range | min–max measurable input |
| Sensitivity | output change per input change |
| Resolution | smallest detectable change |
| Accuracy | closeness to true value |
| Precision | repeatability |
| Linearity | constancy of sensitivity |
| Bandwidth | fastest signal it can track |

Calibration maps raw output to the measured quantity; specs trade off against cost and size.

## Common Sensors

| Quantity | Sensor |
|---|---|
| Position/angle | potentiometer, encoder, resolver, LVDT |
| Acceleration / rotation | accelerometer, gyroscope (MEMS IMU) |
| Force/pressure | strain gauge, load cell, piezoelectric |
| Temperature | thermocouple, RTD, thermistor |
| Proximity/distance | ultrasonic, IR, lidar, capacitive, Hall effect |
| Light | photodiode, phototransistor, camera |

## Measurement Principles

Many sensors exploit a physical law: strain gauges use resistance change \\(\Delta R/R = G_F\varepsilon\\) (gauge factor \\(G_F\\)); thermocouples the Seebeck effect; piezoelectrics charge under stress; Hall sensors voltage in a magnetic field (see [Magnetostatics](../../physics/em/magnetostatics.md)).

## Noise and Error

Real signals carry noise (thermal, shot, interference) and systematic error (offset, drift, hysteresis). Mitigation: shielding, filtering ([signal processing](../electrical/signal-processing.md)), averaging, and **sensor fusion** combining complementary sensors (see [Sensing and Perception](../../app/robotics/sensing.md)).

## See Also

- [Interfacing and Signal Conditioning](interfacing.md)
- [Bioinstrumentation](../../app/biomed/instrumentation.md)
- [Sensing and Perception](../../app/robotics/sensing.md)
