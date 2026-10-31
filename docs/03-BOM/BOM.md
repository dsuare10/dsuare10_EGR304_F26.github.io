---
title: Bill of Materials
tags:
- BOM
- Components
---

## Overview

The Bill of Materials (BOM) provides a complete list of the electrical and electromechanical components required for the laundry-folding robot subsystem. All components used in the schematic are included, including components already available in the Peralta 109 laboratory. Most electronic components and supporting hardware are available from the existing Peralta inventory; therefore, the primary components that must be purchased for this subsystem are the 12 V power supply and the DFRobot FIT0492-A DC gearmotor. The BOM will continue to be updated as the subsystem design is finalized.

## Bill of Materials

| **Part Name/Description** | **Qty** | **Unit Cost** | **Total Cost** | **Manufacturer** | **Manufacturer # / Value** | **Vendor Link** | **Datasheet Link** | **Schematic Reference Designators** |
|:---|:---:|:---:|:---:|:---|:---|:---|:---|:---|
| 12 V, 50 RPM DC Gearmotor | 1 | $11.90 | $11.90 | DFRobot | FIT0492-A | [DigiKey](https://www.digikey.com/en/products/detail/dfrobot/FIT0492-A/7087165) | [Datasheet](https://media.digikey.com/pdf/Data%20Sheets/DFRobot%20PDFs/FIT0492-A_Web.pdf) | M2 |
| 12 V, 5 A, 60 W AC/DC Power Supply | 1 | $19.40 | $19.40 | MEAN WELL | GST60A12-P1J | [DigiKey](https://www.digikey.com/en/products/detail/mean-well-usa-inc/GST60A12-P1J/7703712) | [Datasheet](https://www.meanwell.com/Upload/PDF/GST60A/GST60A-SPEC.PDF) | External Power Supply |
| PIC18F57Q43 Curiosity Nano Development Board | 1 | On Hand | $0.00 | Microchip Technology | DM164150 | Peralta 109 | [Datasheet](https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/DataSheets/PIC18F27-47-57Q43-Data-Sheet-40002147.pdf) | PIC18F57Q43_CuriosityNano_DS1 |
| 5 V Linear Voltage Regulator | 1 | On Hand | $0.00 | STMicroelectronics | L7805CV | Peralta 109 | [Datasheet](https://www.st.com/resource/en/datasheet/l78.pdf) | U2 |
| Quad Operational Amplifier | 1 | On Hand | $0.00 | Microchip Technology | MCP6004-I/P | Peralta 109 | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP6001-1R-1U-2-4-1-MHz-Low-Power-Op-Amp-DS20001733L.pdf) | U1 |
| Reflective IR Emitter/Detector Sensor | 1 | On Hand | $0.00 | TT Electronics/Optek | OPB732 | Peralta 109 | [Datasheet](https://www.digikey.com/htmldatasheets/production/101823/0/0/1/opb732.pdf) | IR Sensor |
| H-Bridge Motor Driver | 1 | On Hand | $0.00 | Texas Instruments | DRV8876PWPR | Peralta 109 | [Datasheet](https://www.ti.com/lit/ds/symlink/drv8876.pdf) | Motor Driver |
| DC Barrel Jack with Switch | 1 | On Hand | $0.00 | Generic | BarrelJack_Switch | Peralta 109 | N/A | J1 |
| 1 A Fuse | 1 | On Hand | $0.00 | Generic | 1 A | Peralta 109 | N/A | F1 |
| 8-Pin Ribbon Cable Connector | 1 | On Hand | $0.00 | Generic | 1x08, 2.54 mm | Peralta 109 | N/A | J2 |
| 5-Pin Header/Connector | 1 | On Hand | $0.00 | Generic | 1x05, 2.54 mm | Peralta 109 | N/A | J3 |
| 8-Pin Header/Connector | 1 | On Hand | $0.00 | Generic | 1x08, 2.54 mm | Peralta 109 | N/A | J4 |
| DPST Debugging Pushbutton/Switch | 2 | On Hand | $0.00 | Generic | SW_DPST | Peralta 109 | N/A | SW2, SW3 |
| Red LED | 1 | On Hand | $0.00 | Generic | Red LED | Peralta 109 | N/A | D1 |
| Indicator LED | 1 | On Hand | $0.00 | Generic | LED | Peralta 109 | N/A | D2 |
| 10 kΩ Potentiometer | 1 | On Hand | $0.00 | Generic | 10 kΩ | Peralta 109 | N/A | RV1 |
| 100 kΩ, 1/4 W Resistor | 2 | On Hand | $0.00 | Generic | 100 kΩ | Peralta 109 | N/A | R1, R8 |
| 10 kΩ, 1/4 W Resistor | 3 | On Hand | $0.00 | Generic | 10 kΩ | Peralta 109 | N/A | R2, R3, R7 |
| 220 kΩ, 1/4 W Resistor | 1 | On Hand | $0.00 | Generic | 220 kΩ | Peralta 109 | N/A | R4 |
| 1 kΩ, 1/4 W Resistor | 3 | On Hand | $0.00 | Generic | 1 kΩ | Peralta 109 | N/A | R5, R6, R10 |
| 4 kΩ, 1/4 W Resistor | 1 | On Hand | $0.00 | Generic | 4 kΩ | Peralta 109 | N/A | R9 |
| 220 Ω, 1/4 W Resistor | 1 | On Hand | $0.00 | Generic | 220 Ω | Peralta 109 | N/A | R11 |
| 0.1 µF, 25 V Capacitor | 2 | On Hand | $0.00 | Generic | 0.1 µF, 25 V | Peralta 109 | N/A | C1, C2 |
| 1 µF, 10 V Capacitor | 1 | On Hand | $0.00 | Generic | 1 µF, 10 V | Peralta 109 | N/A | C3 |
| 0.33 µF, 25 V Capacitor | 1 | On Hand | $0.00 | Generic | 0.33 µF, 25 V | Peralta 109 | N/A | C4 |
| 0.1 µF, 10 V Capacitor | 1 | On Hand | $0.00 | Generic | 0.1 µF, 10 V | Peralta 109 | N/A | C5 |
| PCB Test Point | 7 | On Hand | $0.00 | Generic | Test Point | Peralta 109 | N/A | TP1–TP7 |

## Components Requiring Purchase

The majority of the electrical components required for the subsystem are available from the existing Peralta 109 inventory. The following components are not currently available and will therefore be included in the purchase request:

| **Component** | **Manufacturer #** | **Vendor** | **Qty Required** | **Unit Cost** | **Total** |
|:---|:---|:---|:---:|:---:|:---:|
| 12 V, 50 RPM DC Gearmotor | FIT0492-A | DigiKey | 1 | $11.90 | $11.90 |
| 12 V, 5 A, 60 W AC/DC Power Supply | GST60A12-P1J | DigiKey | 1 | $19.40 | $19.40 |
| **Total Purchase Cost** | | | | | **$31.30** |
