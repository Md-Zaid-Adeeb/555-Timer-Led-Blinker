# 555 Timer LED Blinker — KiCad PCB Project

A simple, complete PCB design built in **KiCad 10** demonstrating a 555 Timer IC configured in **astable multivibrator mode** to blink an LED at a fixed frequency.

![Status](https://img.shields.io/badge/status-complete-brightgreen) ![KiCad](https://img.shields.io/badge/KiCad-10.0.3-blue)

---

## 📋 Overview

This project uses the classic **NE555 timer IC** in astable mode to generate a continuous square wave output, which drives an LED to blink at approximately **1 Hz**. It was built end-to-end in KiCad — from schematic capture to a manufacturing-ready PCB — as a demonstration of the full PCB design workflow.

## ⚙️ Circuit Design

**Astable multivibrator formulas:**
- High time: `T1 = 0.693 × (R1 + R2) × C1`
- Low time: `T2 = 0.693 × R2 × C1`
- Frequency: `f = 1.44 / ((R1 + 2×R2) × C1)`

### Bill of Materials

| Ref | Component | Value | Package |
|-----|-----------|-------|---------|
| U1 | NE555 Timer IC | — | DIP-8 |
| R1 | Resistor | 10kΩ | THT Axial |
| R2 | Resistor | 100kΩ | THT Axial |
| R3 | Resistor (LED current limit) | 330Ω | THT Axial |
| C1 | Capacitor (timing) | 10µF | THT Disc |
| C2 | Capacitor (control voltage decoupling) | 0.01µF | THT Disc |
| D1 | LED | 5mm | THT |
| J1 | Power connector | 2-pin | Pin Header |

### Pin Connections (NE555)

| Pin | Function | Connection |
|-----|----------|------------|
| 1 | GND | Ground rail |
| 2, 6 | Trigger / Threshold | Shorted together (astable config) |
| 3 | Output | → R3 → LED → GND |
| 4 | Reset | Tied to VCC |
| 5 | Control Voltage | → C2 → GND |
| 7 | Discharge | Between R1 and R2 |
| 8 | VCC | Power input |

## 🛠️ Design Process

This project follows the complete PCB design workflow:

1. **Schematic Capture** — Circuit drawn in KiCad Schematic Editor
2. **Electrical Rules Check (ERC)** — Verified 0 errors
3. **Footprint Assignment** — Through-hole packages assigned for easy hand-soldering
4. **PCB Layout** — Components placed and routed on a 2-layer board
5. **Design Rules Check (DRC)** — Verified 0 violations
6. **Board Outline** — Defined using Edge.Cuts layer
7. **3D Visualization** — Reviewed final board appearance
8. **Gerber & Drill File Generation** — Manufacturing-ready output files

## 📁 Repository Structure
├── 555_LED_BLINKER.kicad_pro # KiCad project file
├── 555_LED_BLINKER.kicad_sch # Schematic
├── 555_LED_BLINKER.kicad_pcb # PCB layout
├── gerbers/ # Manufacturing files (Gerber + drill files)
└── README.md
