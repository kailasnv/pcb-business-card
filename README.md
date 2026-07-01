# PCB Business Card

A credit-card sized custom PCB that doubles as a contact card and an interactive embedded demo. Designed from scratch — no dev board, no modules, bare chip bring-up on a custom 2-layer board.

---

## What it does

| Mode | Trigger | Description |
|---|---|---|
| **Scroll** | Idle | Scrolls name and contact details across the 8×8 LED matrix |
| **Flappy Bird** | Button press | Classic Flappy Bird on an 8×8 grid |
| **Ball** | Tilt card | 1-pixel ball rolls around the matrix responding to physical tilt |

---

## Hardware

| Component | Part | Purpose |
|---|---|---|
| MCU | STM32G071RBT6 (LQFP-64) | Main processor, Cortex-M0+ @ 64MHz |
| LED Driver | MAX7219 (SOIC-24) | Drives 8×8 LED matrix over SPI |
| Display | 8×8 red LED matrix (0603 LEDs) | Output display |
| Accelerometer | IIS2DLPC (LGA-12) | 3-axis tilt sensing over I²C |
| Charger | TP4056 (SOP-8) | LiPo charging via USB-C |
| Regulator | MCP1700-3.3 | 3.3V LDO from LiPo |
| Power | 3.7V 1500mAh LiPo | Battery |
| Input | SMD tactile switch (3×6mm) | Game button |
| Connector | USB-C (16-pin SMD) | Charging input |


---



## Schematic overview

Five sub-circuits:
- **Power** — USB-C → TP4056 → LiPo → MCP1700 → 3.3V rail
- **MCU** — STM32G071RB with decoupling, BOOT0 pull-down, SWD pads
- **LED matrix** — MAX7219 driven over SPI, 64× 0603 red LEDs in 8×8 grid
- **Accelerometer** — IIS2DLPC over I²C with pull-ups, interrupt lines to MCU
- **Input** — Tactile button + 4-pad SWD debug port

---

## Firmware (in progress)

---
