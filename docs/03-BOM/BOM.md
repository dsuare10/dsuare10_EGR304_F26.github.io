---
title: Bill of Materials
tags:
- BOM
- Components
---

## Overview

The Bill of Materials (BOM) provides a complete list of the electrical and electromechanical components required for the laundry-folding robot subsystem. The component quantities, values, and schematic reference designators are based on the BOM generated from the current KiCad schematic. All components are included regardless of whether they must be purchased or are already available in the Peralta 109 laboratory. Most electronic components and supporting hardware are available from Peralta 109; therefore, the primary components that must be purchased are the DFRobot FIT0492-A DC gearmotor and the MEAN WELL GST60A12-P1J 12 V power supply.

## Bill of Materials

| **Part Name/Description** | **Qty** | **Unit Cost** | **Total Cost** | **Manufacturer** | **Manufacturer # / Value** | **Vendor Link** | **Datasheet Link** | **Schematic Reference Designators** |
|:---|:---:|:---:|:---:|:---|:---|:---|:---|:---|
| 12 V, 50 RPM DC Gearmotor | 1 | $11.90 | $11.90 | DFRobot | FIT0492-A | [DigiKey](https://www.digikey.com/en/products/detail/dfrobot/FIT0492-A/7087165) | [Datasheet](https://media.digikey.com/pdf/Data%20Sheets/DFRobot%20PDFs/FIT0492-A_Web.pdf) | M2 |
| 12 V, 5 A, 60 W AC/DC Power Supply | 1 | $19.40 | $19.40 | MEAN WELL | GST60A12-P1J | [DigiKey](https://www.digikey.com/en/products/detail/mean-well-usa-inc/GST60A12-P1J/7703712) | [Datasheet](https://www.meanwell.com/Upload/PDF/GST60A/GST60A-SPEC.PDF) | External Power Supply |
| PIC18F57Q43 Curiosity Nano Development Board | 1 | On Hand | $0.00 | Microchip Technology | PIC18F57Q43 Curiosity Nano | Peralta 109 | [Datasheet](https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/DataSheets/PIC18F27-47-57Q43-Data-Sheet-40002147.pdf) | PIC18F57Q43_CuriosityNano_DS1 |
| Quad Operational Amplifier | 1 | On Hand | $0.00 | Microchip Technology | MCP6004 | Peralta 109 | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP6001-1R-1U-2-4-1-MHz-Low-Power-Op-Amp-DS20001733L.pdf) | U1 |
| 5 V Linear Voltage Regulator | 1 | On Hand | $0.00 | STMicroelectronics | L7805 | Peralta 109 | [Datasheet](https://www.st.com/resource/en/datasheet/l78.pdf) | U2 |
| FAN8011N Motor Driver | 1 | On Hand | $0.00 | Onsemi | FAN8011N | Peralta 109 | N/A | FAN8011N_DS2 |
| NPN Phototransistor | 1 | On Hand | $0.00 | Generic | Q_Photo_NPN | Peralta 109 | N/A | Q1 |
| DC Barrel Jack with Switch | 1 | On Hand | $0.00 | Generic | Barrel_Jack_Switch | Peralta 109 | N/A | J1 |
| 1 A Fuse | 1 | On Hand | $0.00 | Generic | 1 A | Peralta 109 | N/A | F1 |
| 8-Pin Connector | 2 | On Hand | $0.00 | Generic | Conn_01x08 | Peralta 109 | N/A | J2, J4 |
| 5-Pin Connector | 1 | On Hand | $0.00 | Generic | Conn_01x05 | Peralta 109 | N/A | J3 |
| Red LED | 1 | On Hand | $0.00 | Generic | RED LED | Peralta 109 | N/A | D1 |
| Indicator LED | 1 | On Hand | $0.00 | Generic | LED | Peralta 109 | N/A | D2 |
| DPST Pushbutton/Switch | 2 | On Hand | $0.00 | Generic | SW_DPST | Peralta 109 | N/A | SW2, SW3 |
| 10 kΩ Potentiometer, 1/4 W | 1 | On Hand | $0.00 | Generic | 10 kΩ, 1/4 W | Peralta 109 | N/A | RV1 |
| 100 kΩ Resistor, 1/4 W | 2 | On Hand | $0.00 | Generic | 100 kΩ, 1/4 W | Peralta 109 | N/A | R1, R8 |
| 10 kΩ Resistor, 1/4 W | 2 | On Hand | $0.00 | Generic | 10 kΩ, 1/4 W | Peralta 109 | N/A | R2, R3 |
| 220 kΩ Resistor, 1/4 W | 2 | On Hand | $0.00 | Generic | 220 kΩ, 1/4 W | Peralta 109 | N/A | R4, R7 |
| 1 kΩ Resistor, 1/4 W | 3 | On Hand | $0.00 | Generic | 1 kΩ, 1/4 W | Peralta 109 | N/A | R5, R6, R10 |
| 4 kΩ Resistor, 1/4 W | 1 | On Hand | $0.00 | Generic | 4 kΩ, 1/4 W | Peralta 109 | N/A | R9 |
| 220 Ω Resistor, 1/4 W | 1 | On Hand | $0.00 | Generic | 220 Ω, 1/4 W | Peralta 109 | N/A | R11 |
| 0.1 µF Capacitor, 25 V | 2 | On Hand | $0.00 | Generic | 0.1 µF, 25 V | Peralta 109 | N/A | C1, C2 |
| 0.1 µF Capacitor, 10 V | 1 | On Hand | $0.00 | Generic | 0.1 µF, 10 V | Peralta 109 | N/A | C3 |
| 0.33 µF Capacitor, 25 V | 1 | On Hand | $0.00 | Generic | 0.33 µF, 25 V | Peralta 109 | N/A | C4 |
| 0.1 µF Capacitor, 10 V | 1 | On Hand | $0.00 | Generic | 0.1 µF, 10 V | Peralta 109 | N/A | C5 |
| PCB Test Point | 7 | On Hand | $0.00 | Generic | TestPoint | Peralta 109 | N/A | TP1, TP2, TP3, TP4, TP5, TP6, TP7 |

## Components Requiring Purchase

Most components required for the subsystem are available from the existing Peralta 109 inventory. The following components must be purchased for the subsystem:

| **Part Name/Description** | **Qty** | **Unit Cost** | **Total Cost** | **Manufacturer** | **Manufacturer #** | **Vendor Link** |
|:---|:---:|:---:|:---:|:---|:---|:---|
| 12 V, 50 RPM DC Gearmotor | 1 | $11.90 | $11.90 | DFRobot | FIT0492-A | [DigiKey](https://www.digikey.com/en/products/detail/dfrobot/FIT0492-A/7087165) |
| 12 V, 5 A, 60 W AC/DC Power Supply | 1 | $19.40 | $19.40 | MEAN WELL | GST60A12-P1J | [DigiKey](https://www.digikey.com/en/products/detail/mean-well-usa-inc/GST60A12-P1J/7703712) |
| **Total Purchase Cost** | **2** | | **$31.30** | | | |
