# IoT-Based Radiation Exposure Monitoring & Alert Concept

> **Educational concept / classroom demonstration only. This prototype did not measure radiation.**

## Overview

This project explores an IoT alert concept for ionising-radiation work areas, such as environments involving X-ray or CT equipment. The classroom demonstration used an ESP32, a potentiometer as a simulated sensor input, a red LED, and a buzzer. The ESP32 read the changing analogue input and used a threshold condition to trigger local alerts.

The original idea was to explore how personnel working around medical imaging equipment might receive an additional warning when a suitable monitoring input indicates a condition above a configured threshold. A supervisor-facing dashboard and connected monitoring were considered as future extensions; they are not described here as completed features.

## Demonstration components

| Component | Role |
|---|---|
| ESP32 development board | Reads analogue input and runs threshold logic |
| Potentiometer | Simulates a changing sensor reading |
| Breadboard and jumper wires | Temporary circuit assembly |
| Red LED | Visual alert output |
| Buzzer | Audible alert output |
| Arduino development environment | Microcontroller programming context |

## Demonstration flow

1. Adjust the potentiometer to change the analogue input.
2. The ESP32 reads the analogue value.
3. The program compares the simulated value with a configured threshold.
4. When the alert condition is met, the red LED and buzzer provide local feedback.

## What this demonstrates

- Reading an analogue input with a microcontroller.
- Applying a threshold-based decision rule.
- Triggering visual and audible outputs.
- Using a potentiometer to simulate sensor values safely in a classroom demonstration.

## Important technical and safety limitations

- **No actual radiation was detected or measured.** The potentiometer only simulated a sensor signal.
- No Geiger-Müller tube, calibrated radiation detector, survey meter, or personal dosimeter was used.
- The demonstration does not measure dose rate or cumulative dose and must not be used to make safety decisions.
- It is not tested, calibrated, certified, or suitable for clinical, industrial, or occupational safety use.
- A future real version would require a suitable detector, professional calibration and validation, fail-safe design, and regulatory review.
- A dashboard, cloud connection, remote alerting, and persistent logging are proposed extensions unless separately implemented and verified.

### Important scope clarification: X-ray/CT vs MRI

X-ray, CT, and fluoroscopy systems use ionising radiation. MRI uses strong magnetic fields and radiofrequency energy and does not use ionising radiation. Therefore, this concept is framed around ionising-radiation work areas; MRI safety requires a separate approach.

## Future work

1. Define the exact ionising-radiation use case.
2. Select a suitable detector for the radiation type and measurement range.
3. Establish calibration, accuracy, alarm thresholds, and controlled validation.
4. Add sensor-fault, power-failure, and communication-loss handling.
5. Develop secure data transmission and a supervisor dashboard only after sensing is validated.
6. Obtain qualified radiation-safety and regulatory review before any operational deployment.

## Portfolio description

Explored an IoT-based radiation-alert concept using an ESP32. Built a classroom demonstration in which a potentiometer simulated changing sensor readings and a threshold condition activated a red LED and buzzer. The prototype demonstrated analogue-input processing and local alerts; it did not measure actual radiation.

## References

- U.S. FDA — [Medical X-ray Imaging](https://www.fda.gov/radiation-emitting-products/medical-imaging/medical-x-ray-imaging)
- U.S. FDA — [MRI (Magnetic Resonance Imaging)](https://www.fda.gov/radiation-emitting-products/medical-imaging/mri-magnetic-resonance-imaging)
- Atomic Energy Regulatory Board (India) — [RTI Queries & Responses](https://aerb.gov.in/english/transparency-open-government/rti/rti-faq-s)

---

**Documentation note:** Exact circuit pin assignments, resistor values, firmware source, network implementation, and measured test results were not available for this write-up and are not claimed.
