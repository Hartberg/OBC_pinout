# OBC Controller Board Pinout

The `Pinout` columns have the following meanings:

| Column | Meaning |
| --- | --- |
| `Position` | Physical package-pin position. |
| `Name` | Microcontroller pin or power/system-pin name. |
| `Type` | Pin classification: `I/O`, `Output`, `Power`, `Reset`, `MonoIO`, or `Boot`. |
| `Signal` | Function currently selected for the board. |
| `Label` | Board-level name used when `Signal` is `GPIO_Output`. |
| `AF0`–`AF14` | Alternate functions available on that microcontroller pin. These are reference options, not additional active assignments. |

An empty `Signal` cell means that the workbook does not currently assign a peripheral or GPIO function to that position. It does not mean that a power, reset, boot, oscillator, or other system pin can be left unconnected.

## Active pin assignments

### SPI

| Bus | Function | MCU pin | Position | Selected signal |
| --- | --- | --- | ---: | --- |
| SPI4 | Clock | PE2 | 1 | `SPI4_SCK` |
| SPI4 | Chip select 1 | PE3 | 2 | `GPIO_Output` (`SPI4-CS1`) |
| SPI4 | Chip select 2 | PE4 | 3 | `GPIO_Output` (`SPI4-CS2`) |
| SPI4 | MISO | PE5 | 4 | `SPI4_MISO` |
| SPI4 | MOSI | PE6 | 5 | `SPI4_MOSI` |
| SPI2 | MISO | PC2_C | 30 | `SPI2_MISO` |
| SPI2 | MOSI | PC3_C | 31 | `SPI2_MOSI` |
| SPI2 | Chip select 1 | PB12 | 72 | `GPIO_Output` (`SPI2-CS1`) |
| SPI2 | Clock | PD3 | 115 | `SPI2_SCK` |
| SPI2 | Chip select 2 | PB9 | 137 | `GPIO_Output` (`SPI2-CS2`) |
| SPI6 | Chip select | PA4 | 43 | `SPI6_NSS` |
| SPI6 | Clock | PA5 | 44 | `SPI6_SCK` |
| SPI6 | MISO | PA6 | 45 | `SPI6_MISO` |
| SPI6 | MOSI | PA7 | 46 | `SPI6_MOSI` |

### I²C

| Bus | Function | MCU pin | Position |
| --- | --- | --- | ---: |
| I2C1 | SCL | PB6 | 133 |
| I2C1 | SDA | PB7 | 134 |
| I2C2 | SCL | PB10 | 66 |
| I2C2 | SDA | PB11 | 67 |
| I2C4 | SCL | PF14 | 53 |
| I2C4 | SDA | PF15 | 54 |

### UART and USART

| Interface | TX pin | TX position | RX pin | RX position |
| --- | --- | ---: | --- | ---: |
| USART1 | PA9 | 98 | PA10 | 99 |
| USART2 | PD5 | 117 | PD6 | 120 |
| USART3 | PD8 | 76 | PD9 | 77 |
| UART5 | PB13 | 73 | PB5 | 132 |
| UART7 | PE8 | 58 | PE7 | 57 |
| UART8 | PE1 | 139 | PE0 | 138 |

### SD/MMC

| Interface | Function | MCU pin | Position |
| --- | --- | --- | ---: |
| SDMMC1 | D0 | PC8 | 95 |
| SDMMC1 | D1 | PC9 | 96 |
| SDMMC1 | D2 | PC10 | 109 |
| SDMMC1 | D3 | PC11 | 110 |
| SDMMC1 | Clock | PC12 | 111 |
| SDMMC1 | Command | PD2 | 114 |
| SDMMC2 | Clock | PC1 | 29 |
| SDMMC2 | Command | PA0 | 37 |
| SDMMC2 | D0 | PB14 | 74 |
| SDMMC2 | D1 | PB15 | 75 |
| SDMMC2 | D2 | PG11 | 124 |
| SDMMC2 | D3 | PB4 | 131 |

### USB, CAN, and debug

| Interface | Function | MCU pin | Position |
| --- | --- | --- | ---: |
| USB OTG FS | D− | PA11 | 100 |
| USB OTG FS | D+ | PA12 | 101 |
| FDCAN1 | RX | PD0 | 112 |
| FDCAN1 | TX | PD1 | 113 |
| SWD/JTAG | SWDIO / JTMS | PA13 | 102 |
| SWD/JTAG | SWCLK / JTCK | PA14 | 107 |
| JTAG | JTDI | PA15 | 108 |
| Trace | SWO / JTDO | PB3 | 130 |

### PWM outputs

| Board label | MCU pin | Position |
| --- | --- | ---: |
| `PWM1` | PE13 | 63 |
| `PWM2` | PA3 | 40 |
| `PWM3` | PE14 | 64 |
| `PWM4` | PA2 | 39 |
| `PWM5` | PE11 | 61 |
| `PWM6` | PD13 | 83 |
| `PWM7` | PD12 | 82 |
| `PWM8` | PD14 | 84 |
| `PWM9` | PD15 | 85 |
| `PWM10` | PC6 | 93 |
| `PWM11` | PC7 | 94 |
| `PWM_PUMP` | PA8 | 97 |


### Enables and indicators

| Board label | MCU pin | Position | Mode |
| --- | --- | ---: | --- |
| `Enable_1` | PG9 | 122 | GPIO output |
| `Enable_2` | PD7 | 121 | GPIO output |
| `Enable_3` | PG13 | 126 | GPIO output |
| `Enable_8` | PG14 | 127 | GPIO output |
| `Debug_LED_R` | PB0 | 49 | GPIO output |
| `Debug_LED_G` | PB1 | 50 | GPIO output |
| `Debug_LED_B` | PB2 | 51 | GPIO output |

Only enables 1, 2, 3, and 8 are present in the current workbook.

### Oscillators and system pins

| Function | MCU pin | Position |
| --- | --- | ---: |
| Low-speed oscillator input | PC14-OSC32_IN | 10 |
| Main oscillator input | PH0-OSC_IN | 25 |
| Reset | NRST | 27 |
| Analog reference | VREF+ | 35 |
| Boot selection | BOOT0 | 135 |

The oscillator output pins are also listed in the workbook—PC15-OSC32_OUT at position 11 and PH1-OSC_OUT at position 26—but their `Signal` cells are empty.

## Power pins

The workbook includes 42 positions classified as power pins:

| Pin name | Count |
| --- | ---: |
| VDD | 13 |
| VSS | 13 |
| VCAP | 3 |
| VDDLDO | 3 |
| VBAT | 1 |
| VSSSMPS | 1 |
| VLXSMPS | 1 |
| VDDSMPS | 1 |
| VFBSMPS | 1 |
| VSSA | 1 |
| VDDA | 1 |
| VDD50_USB | 1 |
| VDD33_USB | 1 |
| PDR_ON | 1 |

Use the exact package positions in `pinout.xlsx` when reviewing the schematic. This summary does not replace the power-supply, decoupling, analog-reference, USB-supply, or internal-regulator requirements in the microcontroller datasheet.

## Updating the pinout

1. Edit the `Pinout` sheet.
2. Keep `Position` and `Name` aligned with the package pinout from the correct microcontroller datasheet.
3. Put the active peripheral function in `Signal`.
4. For a plain GPIO output, set `Signal` to `GPIO_Output` and put the schematic-facing name in `Label`.
5. Confirm that peripheral selections match the correct `AF0`–`AF14` entry. Oscillator and other dedicated system functions may not appear in those columns.
6. Check the new assignment against the schematic, firmware configuration, electrical requirements, and existing uses of the same peripheral signal.
7. Regenerate or update `pinout CSV` so it remains an exact serialization of `Pinout`; the workbook contains no formulas that synchronize the sheets automatically.
8. Record the board revision and describe the change in version control.

## Recommended repository metadata

Add the following details when known:

- Microcontroller manufacturer and exact orderable part number
- Package name and pin count
- Board name and hardware revision
- Schematic document and revision
- Workbook owner and last review date
- Firmware project or generated pin-configuration file
- Connector-to-signal mapping
- Logic levels, pull-ups, default output states, and active-high/active-low conventions


