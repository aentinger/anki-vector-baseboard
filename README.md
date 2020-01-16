This repositories contains my notes after taking a look at the baseboard (**rev. D**) of the Anki Vector robot. **I take no responsibility for whatever you might do with the information found on this page.**

## Power Supply
The voltage level of the pins exposed by the charger is **5V**. Therefore it is necessary to supply Vector with a 5V source when providing power with an external power supply.

## Components
The MCU found on the baseboard is a **STM32F030C8T6** in a **LQFP48** package.

## Connectors
### Head Motor Connector (P1)
| Pin # | Cable Colour | Pin Label | Testpoint | Functional Description |
|:-----:|:------------:| --------- |:---------:| ---------------------- |
| 1     | BN           | CAI       | HENCK     | Head Encoder Clock     |
| 2     | YE           | E2        | HENCB     | Head Encoder Output B  |
| 3     | GN           | E1        | HENCA     | Head Encoder Output A  |
| 4     | WH           | VDD       |           |                        |
| 5     | BK           | Motor -   |           |                        |
| 6     | RD           | Motor +   |           |                        |

### Lift Motor Connector (P2)
| Pin # | Cable Colour | Pin Label | Testpoint | Functional Description |
|:-----:|:------------:| --------- |:---------:| ---------------------- |
| 1     | BN           | CAI       | LENCK     | Lift Encoder Clock     |
| 2     | YE           | E2        | B         | Lift Encoder Output B  |
| 3     | GN           | E1        | A         | Lift Encoder Output A  |
| 4     | WH           | VDD       |           |                        |
| 5     | BK           | Motor -   |           |                        |
| 6     | RD           | Motor +   |           |                        |

### Head Connector (P9)
| Pin # | Cable Colour | Pin Label | Testpoint/Debug Connector |
|:-----:|:------------:| --------- |:-------------------------:|
| 1     | GN           | TX1.8     |                           |
| 2     | WH           | BODY_RX   |                           |
| 3     | BK           | GND       |                           |
| 4     | RD           | VMAIN     | (DC) BAI                  |

### Front Sensor Connector (P?)
| Pin # | Cable Colour | Pin Label | Testpoint/Debug Connector | Functional Description |
|:-----:|:------------:| --------- |:-------------------------:| ---------------------- |
| 1     | RD           | VDD       | VDD (TP)                  | Sensor Power +         |
| 2     | YE           | SCL1      |                           | I2C SCL1               |
| 3     | GN           | SDA1      |                           | I2C SDA1               |
| 4     | BK           | GND       | GND (DC)                  | Sensor Power -         |

### Debug Connector (DC)
There is an unpopulated 7-pin debug header on the back/right corner of the baseboard.

| Pin # | Pin Label | Functional Description                                         |
|:-----:|:---------:| -------------------------------------------------------------- |
| 1     | VX        | External Power Supply (connected with + of charger connector ) |
| 2     | BAI       | Internal Power Supply for head                                 |
| 3     | TX        | STM32F030C8T6 Pin #12 (PA2 = USART2_TX)                        |
| 4     | SWCLK     | STM32F030C8T6 Pin #37 (PA14 = SWCLK)                           |
| 5     | SWDIO     | STM32F030C8T6 Pin #34 (PA13 = SWDIO)                           |
| 6     | NRST      | STM32F030C8T6 Pin #7 (NRST)                                    |
| 7     | GND       |                                                                |

### Other testpoints (TP)
| Testpoint # | Layer           | Testpoint Label | Functional Description                                                  |
|:-----------:|:---------------:|:---------------:| ----------------------------------------------------------------------- |
| 1           | Bottom          | VDD             | Baseboard MCU Power Supply (connected to Pin #1 (VDD) of STM32F030C8T6) |
| 2           | Bottom          | BODY_TX         |                                                                         |
| 3           | Top             | SCL2            | STM32F030C8T6 Pin #35 (PF6 = I2C2_SCL)                                  |
| 4           | Top             | SDA2            | STM32F030C8T6 Pin #36 (PF7 = I2C2_SDA)                                  |
