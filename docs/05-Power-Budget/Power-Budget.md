---
title: Power Budget
---

## Overview

A power budget was created to determine the electrical power requirements of the laundry-folding robot and ensure that the selected power sources and voltage regulators can safely supply all components. Each major electrical component was identified along with its required supply voltage and maximum current consumption. The components were then separated into the appropriate 12 V and 5 V power rails, and their current requirements were totaled. A 25% safety margin was included to account for variations in current consumption and provide additional capacity during operation. The power budget also allows the selected regulators and power supplies to be compared against the calculated system requirements, helping identify components that may need to be changed before the final design is implemented.

<img width="2312" height="1648" alt="Screenshot 2026-10-30 222844" src="https://github.com/user-attachments/assets/788dee91-dc19-447c-8d49-076436698844" />

<img width="2312" height="1503" alt="Screenshot 2026-10-30 223055" src="https://github.com/user-attachments/assets/be33343b-ce76-4be0-b696-1bd6c791f856" />

## Conclusions

From the prepared Power Budget, the power requirements of the major electrical components were evaluated to determine whether the selected power sources and regulators can adequately support the system. The components were separated between the 12 V and 5 V power rails, and a 25% safety margin was included when determining the required current capacity. The results show that the 5 V rail can provide sufficient current for the microcontroller, IR sensor, and op-amp. However, the 12 V rail requires additional current capacity due primarily to the high maximum current of the DC motor. Therefore, the motor, motor driver, and 12 V power supply should be reevaluated to ensure that the final design can safely provide the required current under worst-case operating conditions.

## Resouces

The power budget as a PDF download is available [*here*](PowerBudget(final).pdf), and a Microsoft Excel Sheet [*here*](Power-Budget/PowerBudget_Laundry_Folding_Robot_CORRECTED%(1).xlsx).
