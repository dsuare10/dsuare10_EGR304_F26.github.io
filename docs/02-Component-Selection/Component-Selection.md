---
title: Component Selection
---

# Component Selection

This page compares the components considered for the laundry-folding robot. Each section compares several possible solutions based on electrical requirements, cost, performance, and compatibility with the overall system.

---

## DC Motor

### Option 1 — DFRobot FIT0492-B

<img width="1282" height="804" alt="Screenshot 2026-10-16 190143" src="https://github.com/user-attachments/assets/fa9365bd-308b-4e2f-8b41-d5457eb64b82" />


* **Voltage:** 12 V
* **Part:** DFRobot FIT0492-B
* **Torque:** 686.5 mN·m
* **Price:** $11.90
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/dfrobot/FIT0492-B/7087168?s=N4IgTCBcDaICIDEBKB7ARigLgAgQSQBUAGAFgE4wBaAIRAF0BfIA)

| Pros | Cons |
| --- | --- |
| Operates from 12 V, matching the planned motor power rail. | Does not have built-in position control. |
| Gearbox provides substantially more torque than a basic high-speed DC motor. | At approximately 100 RPM, the motor may move the folding panel too quickly without PWM speed reduction. |
| Approximately $11.90, making it potentially viable within the $60 project budget. | Additional feedback such as limit switches or an encoder may be needed for repeatable 180° movement. |
| Stall current of approximately 2.19 A can be handled by many reasonably priced H-bridge drivers. | Rated torque must still be compared with the actual torque required by the folding panel. |
| Can rotate continuously, making the desired 180° hinge movement mechanically possible. | Multiple motors could consume a significant portion of the project budget. |

### Option 2 — DFRobot FIT0492-A

<img width="1536" height="1226" alt="Screenshot 2026-10-16 192433" src="https://github.com/user-attachments/assets/93770500-0e99-4780-969e-d902ee32a19e" />


* **Voltage:** 12 V
* **Part:** DFRobot FIT0492-A
* **Torque:** 883 mN·m
* **Price:** $11.90
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/dfrobot/FIT0492-A/7087165?s=N4IgTCBcDaIGIEkAqAGALATjAWgIIgF0BfIA)

| Pros | Cons |
| --- | --- |
| 50 RPM provides better control of the folding panel than the 100 RPM FIT0492-B. | Does not have a built-in encoder. |
| Higher rated torque of 883 mN·m makes it better suited for lifting a hinged panel and clothing. | Additional position feedback, limit switches, or timing control would be required. |
| At $11.90, it remains reasonable for the $60 project budget. | Actual folding speed will change with panel and clothing load, making time-based positioning less repeatable. |
| A theoretical 180° rotation takes approximately 0.6 seconds at no load. | The PIC cannot directly determine whether the hinge has reached 90° or 180°. |

### Option 3 — DFRobot FIT0186

<img width="1577" height="1411" alt="Screenshot 2026-10-16 193030" src="https://github.com/user-attachments/assets/418513df-807b-42f5-bd82-e4feef252cc8" />


* **Voltage:** 12 V
* **Part:** DFRobot FIT0186
* **Torque:** 1765 mN·m
* **Price:** $16.50
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/dfrobot/FIT0492-A/7087165?s=N4IgTCBcDaIGIEkAqAGALATjAWgIIgF0BfIA)

| Pros | Cons |
| --- | --- |
| Built-in incremental encoder provides position feedback for controlled 90–180° movement. | At $16.50, it is $4.60 more expensive than either FIT0492 motor. |
| PIC can count encoder pulses to determine how far the hinge has rotated. | 251 RPM is much faster than the other candidates. |
| Encoder feedback can improve repeatability with different clothing weights. | PWM or closed-loop control would likely be necessary for smooth movement. |
| Rated torque of 1765 mN·m is substantially higher than either FIT0492 option. | Encoder feedback requires additional PIC inputs and more complicated firmware. |

**Choice:** Option 3: DFRobot FIT0186

**Rationale:** The DFRobot FIT0186 was selected because it provides the highest rated torque of the three motor options at 1765 mN·m and includes a built-in incremental encoder. The encoder is particularly useful for the folding robot because the PIC can use the encoder feedback to determine how far the folding panel has rotated instead of relying only on timing. This should provide more repeatable 90–180° movements when different weights of clothing are placed on the panel. Although the FIT0186 is more expensive and operates at a higher speed than the other options, PWM and encoder feedback can be used to control its motion. Its combination of higher torque and position feedback makes it the best choice for accurately controlling the folding panels.

---

## Photoresistor

### Option 1 — PDV-P8103

<img width="1520" height="890" alt="Screenshot 2026-10-16 202209" src="https://github.com/user-attachments/assets/0cf2b589-2c46-4d8d-89c7-ded1faad053a" />


* **Dark Resistance:** 500 kΩ
* **Light Resistance:** 16–33 kΩ
* **Part:** PDV-P8103
* **Price:** $0.72
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/advanced-photonix/PDV-P8103/480610?utm_source=chatgpt.com)

| Pros | Cons |
| --- | --- |
| At approximately $0.72, it is the least expensive option. | Individual sensors may produce different readings under identical lighting conditions. |
| 16–33 kΩ resistance at 10 lux provides a useful resistance change for detecting light. | Minimum dark resistance is lower than the other candidates. |
| 60 ms rise time and 25 ms fall time are fast compared with the mechanical movement of the robot. | Ambient room lighting can affect readings. |
| Can be connected to the PIC ADC using a simple voltage divider. | Requires the PIC ADC and software to determine significant light changes. |
| Through-hole package makes prototyping and soldering easy. | A detection threshold may need to be calibrated. |

### Option 2 — NSL-19M51

<img width="1520" height="890" alt="Screenshot 2026-10-16 202209" src="https://github.com/user-attachments/assets/ecaaeb7a-8919-47f7-9080-414544e17312" />


* **Dark Resistance:** 20 MΩ
* **Light Resistance:** 20–100 kΩ
* **Part:** NSL-19M51
* **Price:** $1.05
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/advanced-photonix/NSL-19M51/5039794?utm_source=chatgpt.com)

| Pros | Cons |
| --- | --- |
| Minimum dark resistance of 20 MΩ provides a large difference between dark and illuminated conditions. | 20–100 kΩ resistance range at 10 lux is very broad. |
| Large light-to-dark resistance change is useful for detecting changes in light. | More expensive than the PDV-P8103. |
| At approximately $1.05, it has little impact on the project budget. | Ambient lighting may require software calibration. |
| Through-hole package makes prototyping straightforward. | Requires a voltage-divider circuit and ADC processing. |

### Option 3 — PDV-P9203

<img width="1520" height="890" alt="Screenshot 2026-10-16 202209" src="https://github.com/user-attachments/assets/cfede41d-5d95-4678-95cd-9081f3ac5483" />


* **Dark Resistance:** 5 MΩ
* **Light Resistance:** 10–30 kΩ
* **Part:** PDV-P9203
* **Price:** $1.27
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/advanced-photonix/PDV-P9203/480628)

| Pros | Cons |
| --- | --- |
| 5 MΩ minimum dark resistance provides a greater difference between illuminated and dark conditions than the PDV-P8103. | More expensive than the PDV-P8103. |
| 10–30 kΩ resistance at 10 lux is suitable for a PIC ADC voltage divider. | Approximately 70 ms rise time is slightly slower than the PDV-P8103. |
| Approximately 15 ms fall time provides fast response. | Resistance variation between individual sensors must be considered. |
| Through-hole package is convenient for prototyping. | Ambient room lighting can affect output. |
| Low cost has little impact on the overall budget. | Improved specifications provide limited benefit for simple light-change detection. |

**Choice:** Option 1: PDV-P8103

**Rationale:** The PDV-P8103 was selected because it provides the required light-detection capability at the lowest cost of the three options. Its resistance changes significantly between dark and illuminated conditions, allowing the PIC to detect changes in light through a simple voltage-divider circuit connected to its ADC. Its 60 ms rise time and 25 ms fall time are also much faster than the mechanical movement of the folding robot, so a faster sensor is unnecessary. At only $0.72, the PDV-P8103 provides the required functionality while minimizing the impact on the project's $60 budget.

---

## H-Bridge Motor Driver

### Option 1 — MP6612GF-P

<img width="1529" height="1390" alt="Screenshot 2026-10-16 203634" src="https://github.com/user-attachments/assets/5be68a28-a6a8-471e-9145-8b08442b1c16" />


* **Output Current:** 5 A
* **Load Voltage:** 4–40 V
* **Part:** MP6612GF-P
* **Price:** $3.66
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/monolithic-power-systems-inc/MP6612GF-P/24709807?s=N4IgTCBcDaILIAUBsSCMYDiAxAtAkAugL5A)

| Pros | Cons |
| --- | --- |
| 5 A output-current capability provides significant current capacity. | More expensive than the lower-current alternatives. |
| 4–40 V range supports the planned 12 V motor supply. | 5 A capability may be more than necessary. |
| PWM allows the PIC to reduce motor speed. | Surface-mount 20-TSSOP package is difficult to prototype. |
| Supports bidirectional motor operation. | Exposed thermal pad requires careful PCB layout and soldering. |
| Integrated MOSFETs reduce external component count. | Does not provide hinge-position feedback. |

### Option 2 — DRV8876PWPR

<img width="1557" height="1382" alt="Screenshot 2026-10-16 204407" src="https://github.com/user-attachments/assets/7055c0bd-891e-409b-9e1a-75373de66519" />


* **Output Current:** 3.5 A
* **Load Voltage:** 4.5–37 V
* **Part:** DRV8876PWPR
* **Price:** $2.07
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/monolithic-power-systems-inc/MP6612GF-P/24709807?s=N4IgTCBcDaILIAUBsSCMYDiAxAtAkAugL5A)

| Pros | Cons |
| --- | --- |
| 4.5–37 V range supports the 12 V motors. | Less current margin than the 5 A MP6612GF-P. |
| 3.5 A capability exceeds the approximately 2.19 A locked-rotor current of the FIT0492 motors. | Surface-mount component makes prototyping more difficult. |
| PWM enables motor-speed control. | Exposed pad requires appropriate thermal design. |
| Fully integrated H-bridge provides bidirectional operation. | Position feedback is still required. |
| 16-pin package has fewer pins than the MP6612GF-P. | A motor with stall current above 3.5 A would require a different driver. |

### Option 3 — TB67H450FNG,EL

<img width="1566" height="1297" alt="Screenshot 2026-10-16 204701" src="https://github.com/user-attachments/assets/d2fabb34-eff9-4410-acab-231d3ae7bc90" />


* **Output Current:** 3.5 A
* **Load Voltage:** 4.5–44 V
* **Part:** TB67H450FNG,EL
* **Price:** $1.33
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/toshiba-semiconductor-and-storage/TB67H450FNG-EL/10130904?s=N4IgTCBcDaICoCEBsB2AEgFgKwAYBiAcgOIA0AogDIgC6AvkA)

| Pros | Cons |
| --- | --- |
| Approximately $1.33, making it the least expensive H-bridge candidate. | Listed as "Not For New Designs." |
| 3.5 A capability exceeds the approximately 2.19 A locked-rotor current of the FIT0492 motors. | Less current margin than the 5 A MP6612GF-P. |
| 4.5–44 V range supports the planned 12 V supply. | Surface-mount package makes prototyping more difficult. |
| Supports bidirectional motor operation. | Exposed thermal pad requires proper PCB layout. |
| 8-pin package may simplify PCB routing. | Does not provide hinge-position feedback. |

**Choice:** Option 2: DRV8876PWPR

**Rationale:** The DRV8876PWPR was selected because it provides a good balance between current capability, cost, and compatibility with the 12 V motor system. Its 3.5 A output capability provides sufficient current capacity for the approximately 2.19 A locked-rotor current of the FIT0492 motors considered during the design. It also supports PWM control, allowing the PIC to control motor speed and produce smoother folding movements. Unlike the less expensive TB67H450FNG,EL, the DRV8876PWPR is listed as an active component rather than "Not For New Designs." At $2.07, it provides the required bidirectional motor-control functionality without the additional cost of the 5 A MP6612GF-P.

---

## 12 V Power Supply

### Option 1 — MEAN WELL GST60A12-P1J

<img width="1548" height="1453" alt="image" src="https://github.com/user-attachments/assets/8e0c3998-7bc5-4672-83c7-c7730fd1adda" />

* **Output Voltage:** 12 V DC
* **Output Current:** 5 A
* **Power:** 60 W
* **Part:** GST60A12-P1J
* **Price:** $19.40
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/mean-well-usa-inc/GST60A12-P1J/7703712)

| Pros | Cons |
| --- | --- |
| Regulated 12 V output directly matches the planned motor rail. | Uses approximately 32% of the $60 project budget. |
| 5 A output provides useful capacity for motor startup current. | May not support multiple motors simultaneously at stall. |
| 60 W provides significant power capacity. | AC input cord is sold separately. |
| Enclosed AC-to-DC adapter simplifies internal power electronics. | Physically larger than a small wall adapter. |
| Well-documented commercial power supply. | A separate 5 V regulator is still required. |

### Option 2 — TT Electronics PEAD36B-12-B2

<img width="1556" height="793" alt="image" src="https://github.com/user-attachments/assets/394d577a-99ff-4d1d-b5b3-1d1488672927" />

* **Output Voltage:** 12 V DC
* **Output Current:** 3 A
* **Power:** 36 W
* **Part:** PEAD36B-12-B2
* **Price:** $19.15
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/tt-electronics-power-partners-inc/PEAD36B-12-B2/15838860?s=N4IgTCBcDaIAoFECCARAzANgEIFoCMYOWEAugL5A)

| Pros | Cons |
| --- | --- |
| Regulated 12 V output matches the motor rail. | Provides significantly less current than the 5 A option while costing almost the same amount. |
| 3 A output can operate one FIT0492 motor under normal conditions. | Little remaining current capacity during a motor stall. |
| 36 W is greater than the normal running power of a single FIT0492 motor. | Unsuitable for several motors operating simultaneously at high current. |
| Enclosed supply simplifies the system's AC power design. | Small price savings do not compensate for the reduced current capability. |
| Slightly less expensive than the 5 A MEAN WELL supply. | A separate 5 V regulator is still required. |

### Option 3 — MEAN WELL GSM60A12-P1J

<img width="1574" height="1472" alt="image" src="https://github.com/user-attachments/assets/aa4a2dfb-447d-4e50-9504-b722dc26eeeb" />

* **Output Voltage:** 12 V DC
* **Output Current:** 5 A
* **Power:** 60 W
* **Part:** GSM60A12-P1J
* **Price:** $23.90
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/mean-well-usa-inc/GSM60A12-P1J/7703568?s=N4IgTCBcDaIOIGUCyA2ADAQQIxgLQAUsApEAXQF8g)

| Pros | Cons |
| --- | --- |
| 12 V regulated output matches the planned motor rail. | Most expensive of the three options. |
| 5 A capacity exceeds the 3 A PEAD36B-12-B2. | Same 12 V, 5 A output as the less expensive GST60A12-P1J. |
| 60 W provides additional power capacity. | Medical rating provides little functional benefit for this project. |
| Medical-rated adapter with safety approvals. | AC input cord is sold separately. |
| Wide 80–264 VAC input range. | A separate 5 V regulator is still required. |

**Choice:** Option 1: MEAN WELL GST60A12-P1J

**Rationale:** The MEAN WELL GST60A12-P1J was selected because its regulated 12 V output directly matches the robot's planned motor power rail and its 5 A output provides more current capacity than the 3 A PEAD36B-12-B2. The supply can provide up to 60 W, giving the system additional capacity for motor startup current and other electronics. Although the GSM60A12-P1J provides the same 12 V, 5 A, and 60 W output, it costs $23.90 compared with $19.40 for the GST60A12-P1J. Therefore, the GST60A12-P1J provides the required electrical performance at the lower cost.

---

## 5 V DC-DC Converter

### Option 1 — Murata OKI-78SR-5/1.5-W36-C

<img width="1540" height="1398" alt="image" src="https://github.com/user-attachments/assets/7bae041d-6296-4f01-80c2-a86394cb396c" />

* **Input Voltage:** 7–36 V DC
* **Output Voltage:** 5 V DC
* **Output Current:** 1.5 A
* **Power:** 7.5 W
* **Efficiency:** Up to 90.5%
* **Part:** OKI-78SR-5/1.5-W36-C
* **Price:** $6.00
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/murata-power-solutions-inc/OKI-78SR-5-1-5-W36-C/2259781?s=N4IgTCBcDaIPIGkCSBaA7ADgMoCUUFYB6ARgDp8UB1AZgDYUBhEAXQF8g)

| Pros | Cons |
| --- | --- |
| 7–36 V input accepts the robot's 12 V supply. | 1.5 A rating provides essentially no additional current capacity above the specified requirement. |
| 1.5 A maximum output meets the specified 1.5 A requirement. | More expensive than designing around a lower-cost regulator IC. |
| Up to approximately 90.5% efficient. | Switching operation can introduce electrical noise. |
| Three-pin through-hole package is relatively simple to solder. | Non-isolated input and output share a common ground. |
| Requires few external components. | A higher-current regulator would be required if the final power budget exceeds 1.5 A. |

### Option 2 — RECOM R-78E5.0-1.0

<img width="1519" height="1497" alt="image" src="https://github.com/user-attachments/assets/894ace73-5e05-406c-8c7e-8b88c82d4059" />

* **Input Voltage:** 8–28 V DC
* **Output Voltage:** 5 V DC
* **Output Current:** 1 A
* **Power:** 5 W
* **Efficiency:** Up to 91%
* **Part:** R-78E5.0-1.0
* **Price:** $4.51
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/recom-power/R-78E5-0-1-0/4930585?s=N4IgTCBcDaIEoFEDCB5AsgAjgWgOwA4EBWAOgAZsBGckAXQF8g)

| Pros | Cons |
| --- | --- |
| Accepts the robot's 12 V supply. | 1 A output does not meet the currently specified 1.5 A requirement. |
| Costs $1.49 less than the Murata converter. | Provides 0.5 A less capacity than the Murata option. |
| Efficiency can reach approximately 91%. | No current margin if the electronics approach 1 A. |
| Three-pin through-hole package simplifies prototyping. | Switching operation can introduce noise. |
| Includes short-circuit protection. | Would require demonstrating that the complete 5 V subsystem uses less than 1 A. |

### Option 3 — RECOM R-785.0-1.0

<img width="1489" height="1462" alt="image" src="https://github.com/user-attachments/assets/bbe39ebc-dca9-4a95-bfc3-07b8f1a73d06" />

* **Input Voltage:** 6.5–18 V DC
* **Output Voltage:** 5 V DC
* **Output Current:** 1 A
* **Power:** 5 W
* **Efficiency:** Up to 94%
* **Part:** R-785.0-1.0
* **Price:** $10.23
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/recom-power/R-785-0-1-0/2256218?s=N4IgTCBcDaIEoFEDCB5AsgAjgWgOwA4BWAOgAZsBGMkAXQF8g)

| Pros | Cons |
| --- | --- |
| Input range includes the robot's 12 V rail. | 1 A output does not meet the specified 1.5 A requirement. |
| Up to 94% efficiency, the highest of the three options. | More expensive than the $6.00 Murata option despite lower output current. |
| Three-pin through-hole package simplifies integration. | Improved efficiency provides limited practical benefit compared with the Murata converter. |
| Includes short-circuit and over-temperature protection. | Consumes approximately 17% of the project's $60 budget. |
| High efficiency minimizes wasted power and heat. | Switching noise may affect the photoresistor ADC circuit if filtering/layout is poor. |

**Choice:** Option 1: Murata OKI-78SR-5/1.5-W36-C

**Rationale:** The Murata OKI-78SR-5/1.5-W36-C was selected because it is the only one of the three options that meets the currently specified 1.5 A requirement for the robot's 5 V rail. It can accept the robot's 12 V supply and efficiently convert it to a regulated 5 V output, allowing the entire system to operate from the same external 12 V power supply. Its efficiency of up to 90.5% also reduces wasted power and heat compared with a traditional linear regulator. Although the other two converters are also efficient, they provide only 1 A and therefore do not meet the specified 1.5 A requirement. At $6.00, the Murata converter provides the required current while remaining reasonably priced.
