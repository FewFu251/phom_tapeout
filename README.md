# High-Speed Electro-Optic Radix-4 Matrix

## Overview
This proof-of-concept tile implements a 4-ring programmable photonic matrix utilizing P-N junction carrier injection for nanosecond logic state switching. It is designed to offload parallel tensor broadcasts and sequential optical routing from the CPU via a zero-copy memory-mapped C interface.

## Physical Specifications
* **Dimensions:** 500.00 µm x 320.70 µm
* **Process:** SiEPIC OpenEBL (Silicon-on-Insulator)
* **DRC Status:** PASS (Zero Violations)

## Optical I/O Mapping (TE 1550nm Grating Couplers)
* **Input Port:** Coordinates (-220, 0)
* **Output Ports (Match):** 4x Couplers on the right edge.
* **Output Ports (Dump):** 4x Couplers adjacent to Match ports.

## Electrical I/O Mapping (Top Edge Pad Array)
5x 100µm x 100µm Aluminum Pads (100µm spacing).
* **Pad 1 (e11):** Ring 0 P-Junction Control (0.0V - 2.5V)
* **Pad 2 (e12):** Ring 1 P-Junction Control (0.0V - 2.5V)
* **Pad 3 (e13):** Ring 2 P-Junction Control (0.0V - 2.5V)
* **Pad 4 (e14):** Ring 3 P-Junction Control (0.0V - 2.5V)
* **Pad 5 (e15):** Global Common Ground (N-Junction Return)

## Software Interface
Included `photonic_hal.c` demonstrates the procedural memory-mapped I/O required to tune the local ring arrays while maintaining global thermal stabilization.
