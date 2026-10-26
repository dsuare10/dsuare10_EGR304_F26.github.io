---
title: Power Budget
---

## Overview

A power budget was created to determine the electrical power requirements of the laundry-folding robot and ensure that the selected power sources and voltage regulators can safely supply all components. Each major electrical component was identified along with its required supply voltage and maximum current consumption. The components were then separated into the appropriate 12 V and 5 V power rails, and their current requirements were totaled. A 25% safety margin was included to account for variations in current consumption and provide additional capacity during operation. The power budget also allows the selected regulators and power supplies to be compared against the calculated system requirements, helping identify components that may need to be changed before the final design is implemented.

![budget1](<img width="2025" height="1380" alt="Screenshot 2026-10-26 114201" src="https://github.com/user-attachments/assets/a0be18f9-3538-4fca-b6b7-502fae26eff5" />
){style width:"350" height:"300;"}

![budget2](<img width="1989" height="1333" alt="Screenshot 2026-10-26 114212" src="https://github.com/user-attachments/assets/b561e790-fa2e-40cb-b4e6-05b7444b640e" />
){style width:"350" height:"300;"}

![budget3](<img width="2014" height="868" alt="Screenshot 2026-10-26 114220" src="https://github.com/user-attachments/assets/c11f34b0-7714-4c44-8dfe-f37394a6fb66" />
){style width:"350" height:"300;"}

## Conclusions

From the prepared Power Budget, the power requirements of the major electrical components were evaluated to determine whether the selected power sources and regulators can adequately support the system. The components were separated between the 12 V and 5 V power rails, and a 25% safety margin was included when determining the required current capacity. The results show that the 5 V rail can provide sufficient current for the microcontroller, IR sensor, and op-amp. However, the 12 V rail requires additional current capacity due primarily to the high maximum current of the DC motor. Therefore, the motor, motor driver, and 12 V power supply should be reevaluated to ensure that the final design can safely provide the required current under worst-case operating conditions.

## Resouces

The power budget as a PDF download is available [*here*](PowerBudget.pdf), and a Microsoft Excel Sheet [*here*](PowerBudget_Laundry_Folding_Robot&(2).xlsx).
