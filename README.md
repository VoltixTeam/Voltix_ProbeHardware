# Voltix Probe Hardware Design Files

[![Kibot ERC/DRC](https://github.com/VoltixTeam/Voltix_ProbeHardware/actions/workflows/test.yml/badge.svg)](https://github.com/VoltixTeam/Voltix_ProbeHardware/actions/workflows/test.yml)

The Voltix probe lets you program a Voltix module that is soldered onto your PCB or plugged into a breadboard. It has a standard 10-pin 0.1" connector compatible with the popular Tag-Connect cables that allow in-circuit debugging with a very small footprint.

Latest design files:
 - [Schematics](https://voltix-docs.vercel.app/artifacts/probe_hardware/latest/schematics.pdf)
 - [Layout](https://voltix-docs.vercel.app/artifacts/probe_hardware/latest/pcb.pdf)
 - [Assembly plan](https://voltix-docs.vercel.app/artifacts/probe_hardware/latest/assembly.pdf)
 - [3D rendering](https://voltix-docs.vercel.app/artifacts/probe_hardware/latest/3drendering.png)

Specification:
 - Custom debug probe for in-circuit programming/debugging of Voltix modules
 - USB-C connector for connection to a PC
 - Raspberry Pi RP2040 controller handles programming/debugging
 - CMSIS-DAP compatible: Supports programming of the Voltix module via pyOCD/OpenOCD
 - Makes UART output from Voltix module available via USB

![Rendering of Voltix probe](https://voltix-docs.vercel.app/artifacts/probe_hardware/latest/3drendering.png "Voltix probe")

## Firmware

The probe has a dedicated controller (Raspberry Pi RP2040) that manages the upload of new firmware to the Voltix device as well as the communication with a PC. The firmware running on the RP2040 is hosted in [this repository](https://github.com/VoltixTeam/Voltix_ProbeSoftware). To upgrade the firmware on the Voltix probe, connect a wire from one of the ground pins to the test pad labelled 'USB_BOOT' on the bottom of the board, while plugging in the USB cable. A removable storage drive should appear on your PC. Drop a UF2 compatible binary into the drive.
