# STM32-Nucleo64-Clone-PCB
STM32 Nucleo-64 compatible clone PCB designed from scratch in KiCad 9.0
# STM32 Nucleo-64 Compatible Clone PCB

This is an STM32 Nucleo-64 compatible clone PCB designed entirely from scratch
using KiCad 9.0. The project covers the complete design flow from schematic
capture to a fully routed 2-layer PCB with Gerber files ready for manufacturing.

This was built as a personal project to understand how a real development board
is designed at the hardware level. Every pin connection, decoupling network,
debug interface, and power circuit was designed manually without using any
pre-existing template or reference design.


## What is inside this project

The schematic is split into 4 hierarchical sheets.

Sheet 1 covers the power supply circuit including the USB Mini-B input connector,
polyfuse protection, Schottky diode for reverse current blocking, and the
LD1117S33TR 3.3V LDO regulator with all decoupling capacitors.

Sheet 2 covers the main STM32F446RETx target MCU in LQFP-64 package with all
64 pins connected — VDD decoupling caps, VDDA filtering, VBAT, NRST circuit,
HSE and LSE crystals with load capacitors, SWD debug resistors, user LED,
user button, and all GPIO net labels.

Sheet 3 covers the STM32F103CBTx ST-LINK programmer MCU in LQFP-48 package
with USB lines, SWD lines, UART bridge, and all decoupling caps.

Sheet 4 covers all connectors including the ST Morpho headers CN7 and CN10,
Arduino compatible headers CN5, CN6, CN8, and CN9, and the SWD external
debug header CN4.


## Hardware specifications

Main MCU: STM32F446RETx, LQFP-64, ARM Cortex-M4, up to 180MHz

Programmer: STM32F103CBTx, LQFP-48, on-board ST-LINK debugger and programmer

Power input: USB Mini-B 5V with polyfuse and Schottky diode protection

Voltage regulator: LD1117S33TR, SOT-223, 3.3V output

HSE crystal: 8MHz with 18pF load capacitors and 1M feedback resistor

LSE crystal: 32.768kHz with 12pF load capacitors and 1M feedback resistor

Debug interface: SWD header with SWDIO, SWDCLK, SWO, NRST, 3.3V, and GND

Connectors: Arduino Uno compatible headers and ST Morpho dual-row headers
exposing the full MCU pinout

PCB layers: 2-layer with GND copper pour on both top and bottom copper layers

Routing: Auto-routed using FreeRouting v2.1.0 with 0.2mm clearance rules


## Design results

ERC violations: 0 across all 4 schematic sheets

DRC violations: 0 on the routed PCB

Unconnected items after routing: 0


## Tools used

KiCad 9.0 for schematic capture, PCB layout, footprint assignment, and
Gerber generation

FreeRouting v2.1.0 for auto-routing the PCB


## Repository structure

KiCad folder contains the KiCad project file, all schematic sheets,
and the PCB layout file.

Gerbers folder contains all Gerber files and drill files ready for
submission to a PCB manufacturer such as JLCPCB or PCBWay.

Images folder contains screenshots of the 3D view and PCB layout.


## Important note

This is an independent clone designed as a personal project and is not an
exact replica of the official ST Nucleo-64 board. The schematic netlist and
connector pinouts follow the official Nucleo-64 reference as closely as
possible, but component placement, track routing, and board outline differ
from the original ST design. This project is not affiliated with or endorsed
by STMicroelectronics.


## Author

G. Abhilash Reddy

