# Prosthetics and Exoskeletons

Prosthetics **replace** lost limbs; exoskeletons **augment or assist** existing ones. Both are wearable robots that must work in intimate partnership with the human body — a demanding fusion of mechanics, control, and human factors.

## Prosthetic Limbs

A modern prosthesis spans a spectrum of sophistication:
- **Passive** — body-powered or purely mechanical (energy-storing feet, four-bar knees).
- **Microprocessor-controlled** — sensors and a controller adapt damping in real time (e.g. variable-damping knees for stable gait).
- **Powered/active** — motors add net positive energy, enabling stair climbing and natural push-off.

Key design goals: match natural joint dynamics, minimize metabolic cost, and ensure the **socket** interfaces comfortably with residual tissue (often the hardest problem).

## Control and Intent Detection

The central challenge is reading user intent:
- **EMG / myoelectric control** — surface electrodes read residual muscle activity; pattern recognition and ML classify intended motions. See [Reinforcement Learning](../../cs/ml/rl.md) and [Deep Learning](../../cs/ml/deep-learning.md).
- **Targeted muscle reinnervation (TMR)** — surgically rewires nerves to give richer control signals.
- **Finite-state controllers** — switch behavior by gait phase detected from load and motion sensors.

## Exoskeletons

Worn over the body to assist or amplify:
- **Rehabilitation** — guide and support patients relearning movement after stroke or spinal injury.
- **Industrial** — reduce fatigue and injury during lifting.
- **Performance** — reduce metabolic cost of walking/running.

Control must be **transparent** (don't fight the wearer) yet **assistive** at the right moments — typically impedance/admittance control with gait-phase-based assistance. See [Robot Control](../robotics/control.md).

## Human-in-the-Loop Optimization

Because every user differs, modern devices tune assistance parameters online to directly minimize measured metabolic cost or maximize comfort — optimization with the human as part of the loop.

## Materials and Energetics

Lightweight composites (carbon fiber) store and return energy; battery energy density limits powered devices. Comfort, weight, noise, and robustness often matter more to adoption than peak performance.

## See Also

- [Human Motion](motion.md)
- [Robot Control](../robotics/control.md)
- [Rehabilitation Devices](../biomed/rehab.md)
- [Polymers and Composites](../materials-science/polymers.md)
