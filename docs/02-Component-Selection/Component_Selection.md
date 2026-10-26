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

## Reflective IR Sensor

### Option 1 — TT Electronics/Optek OPB732

<img width="1535" height="1301" alt="image" src="https://github.com/user-attachments/assets/5bbe6b4f-7f3c-479b-8e1c-fcc4b94b5a54" />

* **Sensing Method:** Reflective infrared
* **Output Type:** Phototransistor
* **Peak Wavelength:** 850 nm
* **Mounting:** PCB mount
* **Part:** OPB732
* **Price:** Approximately $4.61
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/tt-electronics-optek-technology/OPB732/1637069)

| Pros | Cons |
| --- | --- |
| Designed specifically for non-contact reflective object detection, which is appropriate for detecting clothing on the folding surface. | More expensive than short-range reflective sensors such as the OPB742. |
| Manufacturer documentation states that reflective distances of up to 1 inch or more are possible depending on the external circuitry. | Detection distance depends on the reflectivity and color of the clothing. |
| Phototransistor output provides an analog signal that can be conditioned by an op-amp before being read by the PIC ADC. | Requires external resistors and signal-conditioning circuitry rather than providing a ready-to-use digital output. |
| PCB-mount package can be incorporated directly into the subsystem board. | Ambient infrared light may affect the detector and require threshold calibration. |
| Longer potential sensing range provides more mechanical flexibility when positioning the sensor relative to the clothing. | DigiKey availability should be checked before the final component order. |

### Option 2 — TT Electronics/Optek OPB704WZ

<img width="1555" height="1511" alt="image" src="https://github.com/user-attachments/assets/76b640ea-c99e-4d81-bc6e-bf11e14d3f4b" />

* **Sensing Method:** Reflective infrared
* **Output Type:** Phototransistor
* **Sensing Distance:** Approximately 3.8 mm
* **Mounting:** Chassis mount, pre-wired
* **Part:** OPB704WZ
* **Price:** Approximately $4.61
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/filter/optical-sensors/reflective-analog-output/546)

| Pros | Cons |
| --- | --- |
| Phototransistor output can be amplified or conditioned using the same type of op-amp circuit considered for the OPB732. | Nominal sensing distance is much shorter than the OPB732, requiring the sensor to be positioned close to the clothing. |
| Pre-wired construction can simplify physical placement away from the main PCB. | Chassis-mount construction is less convenient if the sensor is intended to mount directly to the PCB. |
| Reflective sensing allows clothing to be detected without a mechanical switch contacting the garment. | Clothing color and surface reflectivity can change the returned infrared signal. |
| Active DigiKey listing makes it a practical commercial alternative. | External signal-conditioning and threshold calibration are still required. |

### Option 3 — TT Electronics/Optek OPB742

<img width="1562" height="1553" alt="image" src="https://github.com/user-attachments/assets/652f688a-7cd1-4d34-ad10-9e610547d519" />

* **Sensing Method:** Reflective infrared
* **Output Type:** Phototransistor
* **Sensing Distance:** 3.81 mm
* **Mounting:** Through-hole PCB mount
* **Part:** OPB742
* **Price:** Approximately $2.87
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/tt-electronics-optek-technology/OPB742/374792)

| Pros | Cons |
| --- | --- |
| Through-hole PCB mounting is convenient for prototyping and integration into the subsystem board. | 3.81 mm sensing distance requires the clothing to pass very close to the sensor. |
| Approximately $2.87, making it the least expensive of the three IR sensor candidates. | Short sensing range provides less flexibility in the mechanical placement of the sensor. |
| Phototransistor output is compatible with analog signal-conditioning circuitry and the PIC ADC. | Reflective response can vary with clothing color, texture, and distance. |
| Non-contact detection avoids adding a mechanical switch that could interfere with clothing movement. | Requires an external current-limiting resistor for the IR emitter and additional detector circuitry. |

**Choice:** Option 1: TT Electronics/Optek OPB732

**Rationale:** The OPB732 was selected because its reflective infrared sensing method allows the folding robot to detect the presence of clothing without requiring physical contact with the garment. Compared with the OPB704WZ and OPB742, the OPB732 can support a substantially larger reflective sensing distance depending on the external circuitry, providing more flexibility when positioning the sensor relative to the folding surface. Its phototransistor output can be conditioned with an op-amp and then measured by the PIC ADC, allowing the detection threshold to be adjusted for the final mechanical design. Although clothing color and reflectivity can affect the returned infrared signal, calibration can be performed in software and through the signal-conditioning circuit. The longer potential sensing distance and PCB-mount configuration make the OPB732 the best fit for the planned clothing-detection subsystem.

---

## Operational Amplifier

### Option 1 — Microchip MCP6004-I/P

<img width="1549" height="1506" alt="image" src="https://github.com/user-attachments/assets/78965c29-6543-47c9-85b4-3b116efb0609" />

* **Supply Voltage:** 1.8–6 V
* **Number of Amplifiers:** 4
* **Gain Bandwidth Product:** 1 MHz
* **Output Type:** Rail-to-rail
* **Package:** 14-PDIP, through-hole
* **Part:** MCP6004-I/P
* **Price:** Approximately $0.60
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060)

| Pros | Cons |
| --- | --- |
| 1.8–6 V supply range allows operation directly from the planned 5 V rail. | Four amplifier channels require a larger 14-pin package than the two-channel alternatives. |
| Four op-amps in one IC can condition several analog sensor signals without requiring multiple ICs. | Unused amplifier channels must be configured properly if all four are not needed. |
| Rail-to-rail output is useful when interfacing a 5 V analog sensor circuit with the PIC ADC. | More channels than necessary if only one IR detector is ultimately used. |
| 1 MHz gain-bandwidth product is more than sufficient for the relatively slow clothing-detection application. | The circuit still requires external resistors to establish the desired gain and biasing. |
| Through-hole 14-PDIP package is convenient for prototyping and hand soldering. | Slightly more expensive than the LM358P. |

### Option 2 — Microchip MCP6002-I/P

<img width="1544" height="1487" alt="image" src="https://github.com/user-attachments/assets/a0fbff40-4b55-4ff5-9246-058328bdd7f5" />

* **Supply Voltage:** 1.8–6 V
* **Number of Amplifiers:** 2
* **Gain Bandwidth Product:** 1 MHz
* **Output Type:** Rail-to-rail
* **Package:** 8-PDIP, through-hole
* **Part:** MCP6002-I/P
* **Price:** Approximately $0.45
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/microchip-technology/MCP6002-I-P/500875)

| Pros | Cons |
| --- | --- |
| Operates from the same 5 V rail as the MCP6004-I/P. | Provides only two amplifier channels compared with four in the MCP6004-I/P. |
| Rail-to-rail output is well suited to low-voltage sensor signal conditioning. | Additional op-amp ICs would be required if more than two analog channels need conditioning. |
| Smaller 8-pin through-hole package uses less PCB area than the MCP6004-I/P. | Provides little expansion capacity if additional analog sensors are added later. |
| 1 MHz bandwidth is sufficient for the IR clothing-detection circuit. | Still requires external gain-setting and biasing components. |
| Lower unit price than the MCP6004-I/P. | Small cost savings may not justify losing two amplifier channels. |

### Option 3 — Texas Instruments LM358P

<img width="1571" height="1221" alt="image" src="https://github.com/user-attachments/assets/0c0883fd-122b-43ee-a558-97092669c71d" />

* **Supply Voltage:** 3–30 V
* **Number of Amplifiers:** 2
* **Gain Bandwidth Product:** 700 kHz
* **Package:** 8-PDIP, through-hole
* **Part:** LM358P
* **Price:** Approximately $0.33
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/texas-instruments/LM358P/277042)

| Pros | Cons |
| --- | --- |
| Approximately $0.33, making it the least expensive op-amp candidate. | Output is not rail-to-rail, reducing usable output range when powered from 5 V. |
| 3–30 V supply range includes the planned 5 V rail. | Only two amplifier channels are available. |
| Through-hole 8-PDIP package is straightforward to prototype and solder. | 700 kHz gain-bandwidth product is lower than the MCP6002 and MCP6004, although still adequate for this application. |
| Widely used general-purpose op-amp with simple supporting circuitry. | Higher supply current and input bias current than the MCP600x alternatives. |

**Choice:** Option 1: Microchip MCP6004-I/P

**Rationale:** The MCP6004-I/P was selected because it operates directly from the robot's planned 5 V rail and provides four rail-to-rail op-amp channels in a single through-hole IC. The IR sensor produces a phototransistor signal that may need amplification or buffering before being measured by the PIC ADC, and the MCP6004 provides sufficient bandwidth for this relatively slow sensing application. Compared with the MCP6002-I/P, the MCP6004 provides two additional amplifier channels for future sensors or additional signal-conditioning stages while adding little cost. The LM358P is less expensive, but its output is not rail-to-rail, making the MCP6004 better suited to a low-voltage 5 V analog interface. The combination of four channels, 5 V compatibility, rail-to-rail operation, and a through-hole package makes the MCP6004-I/P the most flexible choice for the subsystem.

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

## 5 V Linear Voltage Regulator

### Option 1 — STMicroelectronics L7805CV

<img width="1559" height="1339" alt="image" src="https://github.com/user-attachments/assets/14611ff6-bb43-4cb7-a3a1-cc6146aca452" />

* **Input Voltage Maximum:** 35 V
* **Output Voltage:** 5 V
* **Output Current:** Up to 1.5 A
* **Package:** TO-220-3, through-hole
* **Part:** L7805CV
* **Price:** Approximately $1.08
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964)

| Pros | Cons |
| --- | --- |
| Fixed 5 V output directly provides the planned logic and sensor power rail. | As a linear regulator, it dissipates the voltage difference between 12 V and 5 V as heat. |
| 35 V maximum input rating comfortably includes the robot's 12 V external supply. | A heatsink may be required if the 5 V rail draws substantial current. |
| Up to 1.5 A output provides more capacity than a 1 A regulator option. | Much less efficient than the DC-DC converter previously considered. |
| Through-hole TO-220 package is easy to prototype, solder, and attach to a heatsink if necessary. | Requires input and output capacitors for stable operation and transient response. |
| Includes over-temperature and short-circuit protection. | The final allowable load current will be limited by thermal dissipation in addition to the nominal current rating. |

### Option 2 — onsemi MC7805CTG

<img width="1549" height="1313" alt="image" src="https://github.com/user-attachments/assets/cb91f030-029c-44f8-8957-a97ef635d131" />

* **Input Voltage Maximum:** 35 V
* **Output Voltage:** 5 V
* **Output Current:** 1 A
* **Package:** TO-220-3, through-hole
* **Part:** MC7805CTG
* **Price:** Approximately $0.99
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/onsemi/MC7805CTG/919333)

| Pros | Cons |
| --- | --- |
| Fixed 5 V output and 35 V maximum input are compatible with the planned 12 V-to-5 V power conversion. | 1 A output rating provides less current capacity than the 1.5 A L7805CV. |
| Through-hole TO-220 package is convenient for prototyping and thermal management. | Linear regulation from 12 V to 5 V produces significant heat at higher load currents. |
| Includes over-temperature and short-circuit protection. | May require a heatsink depending on the final 5 V power budget. |
| Slightly less expensive than the L7805CV. | Lower current capacity provides less room for future 5 V devices. |

### Option 3 — Texas Instruments UA7805CKCS

<img width="1560" height="1360" alt="image" src="https://github.com/user-attachments/assets/4cc7a378-ee63-4e8c-94bc-046c9bafd970" />

* **Input Voltage Maximum:** 25 V
* **Output Voltage:** 5 V
* **Output Current:** Up to 1.5 A
* **Package:** TO-220-3, through-hole
* **Part:** UA7805CKCS
* **Price:** Approximately $2.54
* **Product Link:** [DigiKey Product Page](https://www.digikey.com/en/products/detail/texas-instruments/UA7805CKCS/521612)

| Pros | Cons |
| --- | --- |
| 5 V fixed output and 1.5 A rating provide the same basic output capability required for the subsystem. | More expensive than both the L7805CV and MC7805CTG. |
| 25 V maximum input rating comfortably supports the planned 12 V source. | Linear operation creates the same heat-dissipation concern as the other 7805 regulators. |
| Through-hole TO-220 package is convenient for prototyping and heatsink attachment. | Provides little functional benefit over the less expensive L7805CV for this project. |
| Provides thermal protection and is a direct alternative to other 7805-family regulators. | Requires external capacitors and adequate PCB thermal design. |

**Choice:** Option 1: STMicroelectronics L7805CV

**Rationale:** The L7805CV was selected because it provides the required fixed 5 V output from the robot's 12 V supply while offering up to 1.5 A of output current in an easy-to-use through-hole TO-220 package. Its 35 V maximum input rating provides substantial voltage margin above the planned 12 V input, and its over-temperature and short-circuit protection improve robustness. The MC7805CTG is slightly less expensive but provides only 1 A, while the UA7805CKCS provides similar 1.5 A capability at a higher unit price. The primary disadvantage of the L7805CV is heat dissipation because it is a linear regulator, so the final power budget must be used to determine the actual regulator dissipation and whether a heatsink is necessary. Within the assignment requirement to use a linear voltage regulator, the L7805CV provides the best combination of current capacity, cost, package type, and compatibility with the 12 V system.

