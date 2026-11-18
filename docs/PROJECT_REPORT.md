# Radiation Exposure Monitoring & Alert Concept
## IoT Project Report — Concept and Classroom Demonstration

> **Educational concept / classroom demonstration only. This prototype did not measure radiation and must not be used to make radiation-safety decisions.**

## 1. Project overview

This project explores an Internet of Things (IoT) concept for providing a local warning when a radiation-monitoring input appears to cross a preset threshold in a work area. The original problem context was personnel who maintain or work around medical imaging equipment. The intended benefit is a simple alert that draws attention to a potentially unsafe condition and could, in a future engineered version, be paired with a supervisor-facing monitoring interface.

The student demonstration focused on the basic sensing-and-alert logic: an ESP32 reads a changing analogue input, evaluates it against a threshold, and activates visual and audible indicators when the simulated value is high. It was a learning prototype to demonstrate embedded input handling and alert behaviour, not a validated occupational radiation monitor.

| Project detail | Description |
|---|---|
| Project type | Student IoT concept / proof-of-concept demonstration |
| Controller | ESP32 development board |
| Input used in the demonstration | Potentiometer used to simulate sensor readings |
| Outputs used in the demonstration | Red LED and buzzer |

## 2. Intended application and technical scope

The concept is most appropriately framed around equipment and environments that involve ionising radiation, such as conventional X-ray, computed tomography (CT), and fluoroscopy systems. These imaging modalities use X-rays, which are ionising radiation.

MRI is different: it uses strong magnetic fields and radiofrequency energy and does not use ionising radiation. MRI safety therefore requires a separate approach focused on magnetic-field and radiofrequency hazards rather than an X-ray radiation detector.

## 3. Problem statement and proposed objective

**Problem statement:** Personnel working in areas where ionising radiation is used need reliable radiation-safety controls and appropriate monitoring. The concept asks whether a connected, threshold-based alert node could provide an additional local warning when a properly selected radiation detector reports a value above a configured limit.

**Proposed objective:** Design and eventually evaluate an IoT alert node that can receive readings from a suitable radiation detector, compare those readings with configured alert thresholds, notify nearby personnel through indicators, and make status information available to an authorised supervisor. The current prototype demonstrates only the simulated-input and local-alert portion of this objective.

## 4. Demonstration hardware and tools

| Component | Role in the demonstration | Implementation status |
|---|---|---|
| ESP32 development board | Reads the analogue input and runs the threshold/alert logic | Used |
| Potentiometer | Provides a manually adjustable analogue value to simulate changing sensor readings | Used as a simulator; not a radiation sensor |
| Breadboard and jumper wires | Support temporary circuit assembly and connections | Used |
| Red LED | Provides a visible indication when the alert condition is triggered | Used |
| Buzzer | Provides an audible indication when the alert condition is triggered | Used |
| Arduino development environment | Used to write/upload the microcontroller program | Used / project context |
| Radiation detector (for example, a suitable calibrated detector) | Would provide real radiation measurements in a future version | Not used |
| Network/dashboard service | Could transmit status to a supervisor interface in a future version | Proposed; not established as implemented |

### Important scope note

The demonstration did not measure radiation. The potentiometer supplied an adjustable analogue value to imitate a sensor signal. No Geiger-Müller tube, calibrated radiation detector, dosimeter, radioactive source, or real-world dose measurement was used.

For a future version, describe the target environment as ionising-radiation work areas (for example, X-ray or CT facilities). Do not claim that this prototype monitors MRI radiation.

## 5. How the demonstration works

1. The potentiometer is adjusted to change the analogue input supplied to the ESP32.
2. The ESP32 reads that input value through an analogue input pin.
3. The program compares the simulated value with a threshold configured in the demonstration logic.
4. When the value meets the alert condition, the red LED and buzzer are activated to provide visual and audible feedback.
5. When the input returns below the alert condition, the program can return the indicators to their normal state according to the implemented logic.

The potentiometer makes it possible to demonstrate changing input values without using a radiation source or radiation detector. The demonstration therefore validates only the basic interaction between an analogue input, a decision rule, and local output indicators.

## 6. Concept architecture

The following sequence represents the concept and distinguishes the demonstration from a possible future extension:

`Potentiometer (simulated input) → ESP32 analogue read → Compare with threshold → Red LED + buzzer (local alert) → Future extension: calibrated detector + supervisor view`

The first four blocks describe the demonstration at a high level. The final block is a proposed extension, not a verified feature of the prototype.

| Stage | Function |
|---|---|
| Simulated input — potentiometer | Supplies an adjustable analogue value |
| Controller — ESP32 analogue read | Reads the input |
| Decision — threshold comparison | Compares the input against the configured threshold |
| Local alert — red LED and buzzer | Provides visual and audible feedback |
| Future extension — calibrated detector and supervisor view | Proposed direction for a properly engineered version |

## 7. What was demonstrated

- A microcontroller can read a changing analogue input.
- A configurable threshold can be used to trigger a simple decision.
- A local system can communicate an alert through both a visual indicator (LED) and an audible indicator (buzzer).
- A potentiometer can safely simulate changing input values during a classroom demonstration.

## 8. Limitations and safety boundaries

- **No radiation was detected or measured.** The input was simulated using a potentiometer.
- The prototype did not establish dose rate, cumulative dose, exposure in sieverts, or any other radiation measurement.
- No Geiger-Müller tube, scintillation detector, semiconductor detector, calibrated survey meter, or personal dosimeter was part of the demonstration.
- The prototype was not tested or certified for clinical, industrial, or occupational radiation-safety use.
- A threshold alert in this demonstration must not be interpreted as proof that an area is safe when the alarm is off, or unsafe when the alarm is on.
- A supervisor dashboard, cloud connection, long-term logging, user authentication, and remote alerting are proposed ideas only unless separately implemented and tested.

> **Safety:** This project is an educational electronics demonstration only. It must never replace regulatory monitoring, approved survey instruments, personal dosimeters, site procedures, or advice from a qualified radiation-safety professional.

## 9. Future development roadmap

1. **Define the exact hazard** — Limit the radiation-monitoring use case to ionising-radiation environments. Treat MRI magnetic-field/RF safety as a separate project scope.
2. **Select a suitable detector** — Integrate a detector designed for the relevant radiation type and measurement range. Select it with qualified radiation-protection guidance; do not infer dose from an uncalibrated sensor.
3. **Calibrate and validate** — Use an accredited calibration/measurement process and controlled testing to establish accuracy, response, alarm thresholds, and failure behaviour.
4. **Add resilient alerting** — Consider audible/visual alarms, sensor-fault detection, power-failure behaviour, communication-loss warnings, and a safe state on faults.
5. **Add connectivity and dashboard** — Only after reliable sensing is established, add secure data transmission, access control, event logging, and an authorised supervisor view.
6. **Conduct safety and compliance review** — Review the design against applicable Indian Atomic Energy Regulatory Board requirements and obtain professional assessment before any operational use.

## 10. Learning outcomes

The project provided an introduction to microcontroller-based prototyping, analogue input handling, threshold-based decision logic, breadboard circuit assembly, and combining visual and audible outputs. It also highlighted the difference between a classroom simulation and a safety-critical measurement device, including the importance of sensor selection, calibration, validation, and honest communication of technical limitations.

## 11. Suggested portfolio / CV description

Explored an IoT-based radiation-alert concept using an ESP32. Built a classroom demonstration in which a potentiometer simulated changing sensor readings and a threshold condition activated a red LED and buzzer. The prototype demonstrated analogue-input processing and local alerts; it did not measure actual radiation.

## 12. References and technical notes

1. **U.S. Food and Drug Administration (FDA), “Medical X-ray Imaging.”** Explains that radiography, CT, and fluoroscopy use ionising radiation. https://www.fda.gov/radiation-emitting-products/medical-imaging/medical-x-ray-imaging
2. **U.S. Food and Drug Administration (FDA), “MRI (Magnetic Resonance Imaging)” and “Benefits and Risks.”** Explains that MRI uses strong magnetic fields and radiofrequency energy and does not use ionising radiation. https://www.fda.gov/radiation-emitting-products/medical-imaging/mri-magnetic-resonance-imaging
3. **Atomic Energy Regulatory Board (AERB), India, “RTI Queries & Responses.”** AERB describes personal radiation-monitoring devices/dosimeters, including TLD badges, for radiation workers. https://aerb.gov.in/english/transparency-open-government/rti/rti-faq-s

**Documentation note:** This report is based on the project details available for this student demonstration. Exact circuit pin assignments, resistor values, firmware source, network implementation, and measured test results were not provided and are therefore not claimed here.
