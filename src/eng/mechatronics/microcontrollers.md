# Microcontrollers and Embedded Systems

A **microcontroller (MCU)** is a complete computer on a chip — CPU, memory, and peripherals — that runs the control logic of a mechatronic system in real time. Embedded systems are the brains inside everything from thermostats to pacemakers.

## Anatomy of an MCU

- **CPU core** (e.g. ARM Cortex-M) executing firmware.
- **Memory** — Flash (program) and RAM (data).
- **Peripherals** — the interface to the physical world:

| Peripheral | Use |
|---|---|
| GPIO | digital in/out |
| ADC / DAC | read sensors / output analog |
| PWM (timers) | drive motors, dim LEDs |
| UART / SPI / I²C | talk to chips and modules |
| Interrupts | respond to events promptly |

## Real-Time Behavior

Embedded control must meet **deadlines**, not just compute correctly. Key concepts:
- **Interrupts** preempt the main loop to service time-critical events.
- **Polling vs. interrupt-driven** I/O trade simplicity against responsiveness.
- **RTOS** (FreeRTOS, Zephyr) schedules concurrent tasks with priorities when the logic outgrows a superloop.
- **Sampling rate** must satisfy the [Nyquist criterion](../../signals/sampling.md) and the control bandwidth.

## Firmware and the Control Loop

A typical loop reads sensors (ADC), runs a controller (e.g. [PID](../control/pid.md)), and writes actuator commands (PWM) at a fixed rate set by a timer interrupt — the discrete-time realization of [control theory](../control/README.md).

## Platforms

- **Arduino** — accessible, great for prototyping.
- **STM32 / ESP32 / Raspberry Pi Pico** — capable MCUs for serious embedded work.
- **Raspberry Pi / SBCs** — Linux-class compute for vision and high-level logic (often paired with an MCU for real-time I/O).

## Constraints

Embedded systems live within tight limits on memory, compute, power, and cost — and, in medical/automotive use, stringent **safety and reliability** standards (watchdogs, redundancy, certification).

## See Also

- [Interfacing and Signal Conditioning](interfacing.md)
- [Digital Logic](../electrical/digital.md)
- [PID Control](../control/pid.md)
- [Sampling and Reconstruction](../../signals/sampling.md)
