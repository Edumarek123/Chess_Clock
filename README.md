<div align="center">

# DIY Chess Clock

**An embedded chess-clock project with AVR firmware, displays, buttons, and PCB manufacturing files.**

![MCU](https://img.shields.io/badge/microcontroller-ATmega328P-00979D)
![Hardware](https://img.shields.io/badge/hardware-PCB%20%7C%20AVR-6f42c1)
![Project](https://img.shields.io/badge/type-DIY%20electronics-lightgrey)

</div>

## Contents

- [Overview](#overview)
- [Hardware design](#hardware-design)
- [Bill of materials](#bill-of-materials)
- [Firmware overview](#firmware-overview)
- [Repository structure](#repository-structure)
- [Reproduction workflow](#reproduction-workflow)
- [Validation notes](#validation-notes)
- [License](#license)

## Overview

Chess_Clock is a DIY chess-clock project built around an ATmega328P-PU microcontroller. The repository gathers design drawings, PCB layouts, Gerber manufacturing outputs, component datasheets, a bill of materials, and AVR-oriented code.

The goal is to document both the physical electronics and the firmware that manages two players' clocks, display multiplexing, buttons, and timing.

## Hardware design

The bill of materials identifies these principal components:

- ATmega328P-PU
- 7447 seven-segment decoder/driver
- Two four-digit, common-anode seven-segment displays
- Arcade-style buttons and a reset/enter push button
- Indicator LEDs and resistors
- 4.5–5 V power supply
- PCB and enclosure material

Check the original [List_of_materials.txt](List_of_materials.txt) for the complete list and quantities.

## Firmware overview

The AVR source in [code.txt](code.txt) includes:

- Two player time counters
- Button/interrupt handling
- ADC-based selector input
- Seven-segment display control
- Game state for player 1, player 2, and paused mode

The source uses AVR headers such as `avr/io.h`, `avr/interrupt.h`, and `util/delay.h`.

## Repository structure

```text
Chess_Clock/
├── Blueprints/
├── PCB_layouts/
├── GerberFiles_Clock/
├── datasheets/
├── List_of_materials.txt
├── code.txt
├── LICENSE
└── README.md
```

## Reproduction workflow

1. Review the blueprints and schematic-related materials.
2. Compare the PCB layouts with the Gerber outputs.
3. Verify every component against its datasheet.
4. Confirm display type, microcontroller package, pin mapping, and supply voltage.
5. Inspect and compile the AVR firmware with a compatible AVR toolchain.
6. Test button inputs, display multiplexing, and timing before enclosing the electronics.

The repository does not currently provide a verified PCB revision, complete wiring guide, or tested assembly procedure.

## Validation notes

The BOM and firmware are useful starting points, but the hardware should be independently checked before fabrication. In particular, verify current limits, display-driver compatibility, clock accuracy, and the electrical behavior of all button inputs.

## License

This project is licensed under the **GNU General Public License v3.0 only (GPL-3.0-only)**. You may use, study, modify, and redistribute this project under the terms of the license.

See [LICENSE](LICENSE) for the complete license text. Third-party components and assets remain subject to their own licenses and notices.
