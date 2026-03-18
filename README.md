<div align="center">

# 💡 Automatic Dusk to Dawn Light

![Proteus](https://img.shields.io/badge/Proteus-Simulation-1C79B3?style=for-the-badge&logo=proteus&logoColor=white)
![Hardware](https://img.shields.io/badge/Hardware-Breadboard%20Build-green?style=for-the-badge)
![Course](https://img.shields.io/badge/Course-Electronic%20Devices%20%26%20Circuits%20(Lab)-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![University](https://img.shields.io/badge/Namal%20University-Mianwali-teal?style=for-the-badge)

**Lab Project — Electronic Devices & Circuit (Lab)**

*An automated lighting system using an LDR and BJT that turns lights ON at dusk and OFF at dawn, powered by a 220V AC to 12V DC regulated supply — simulated in Proteus and built on hardware.*

---

</div>

## 📋 Overview

This project implements an **Automatic Dusk to Dawn Light** — a light-sensing control circuit that automatically switches a load (LED/bulb) ON during low ambient light (dusk) and OFF during high ambient light (dawn), eliminating the need for manual intervention.

The system consists of **two stages**: a power supply circuit that converts **220V AC mains to regulated 12V DC**, and a control circuit using an **LDR (Light Dependent Resistor)** and a **BJT (BC547/2N3904)** to detect ambient light levels and drive the output load. The project was both **simulated in Proteus** and **built on a breadboard** with real hardware.

## 🎯 Objectives

- Design and implement an automatic light control system using basic electronic components
- Build a **220V AC to 12V DC** regulated power supply (transformer + bridge rectifier + 7812 regulator)
- Use an **LDR + BJT** voltage divider circuit for ambient light detection
- Achieve **automatic ON/OFF switching** based on ambient light levels
- Validate through both **Proteus simulation** and **hardware breadboard implementation**

## 🏗️ Circuit Architecture

```
┌──────────────────────────────────────────────────────────────────────┐
│              AUTOMATIC DUSK TO DAWN LIGHT SYSTEM                     │
├──────────────────────────────────────────────────────────────────────┤
│                                                                      │
│  STAGE 1: POWER SUPPLY (220V AC → 12V DC)                           │
│                                                                      │
│  ┌──────┐    ┌───────────┐    ┌──────┐    ┌──────┐    ┌──────┐    │
│  │ 220V │───▶│Step-Down  │───▶│Bridge│───▶│1000µF│───▶│ 7812 │──┐ │
│  │ AC   │    │Transformer│    │Rect. │    │Cap   │    │ Reg  │  │ │
│  │ Mains│    │(220→12V)  │    │(4×   │    │Filter│    │      │  │ │
│  └──────┘    └───────────┘    │1N4007│    └──────┘    └──────┘  │ │
│                                └──────┘                     12V DC│ │
│  ═══════════════════════════════════════════════════════════════╪═│
│                                                                 │  │
│  STAGE 2: DUSK TO DAWN CONTROL                                  │  │
│                                                                 ▼  │
│              ┌─────┐                                     ┌──────┐ │
│    12V DC───┤ LDR ├───┬───────────┐                     │100µF │ │
│              └─────┘   │           │                     │Cap   │ │
│                        │      ┌────┴────┐                └──────┘ │
│              ┌─────┐   │      │  BJT    │    ┌─────┐    ┌─────┐  │
│         GND─┤10kΩ ├───┘      │(BC547)  ├───┤220Ω ├───┤ LED │  │
│              └─────┘    ┌────┐│  C      │    └─────┘    │/Bulb│  │
│                         │1kΩ ││  B ──E  │               └─────┘  │
│                         │Pot ││         │                         │
│                         └────┘└─────────┘                         │
│                                                                    │
│  Dark → LDR high R → BJT ON → LED ON                              │
│  Light → LDR low R → BJT OFF → LED OFF                            │
│                                                                    │
└──────────────────────────────────────────────────────────────────────┘
```

## 🔧 Components

| Component | Specification | Quantity | Purpose |
|-----------|--------------|----------|---------|
| **Transformer** | 220V AC → 12V AC | 1 | Step-down mains voltage |
| **Diodes** | 1N4007 | 4 | Bridge rectifier (AC → pulsating DC) |
| **Voltage Regulator** | 7812 | 1 | Regulate output to steady 12V DC |
| **Capacitor** | 1000 µF | 1 | Smoothing filter (reduce ripples) |
| **Capacitor** | 100 µF | 1 | Output filtering |
| **LDR** | Light Dependent Resistor | 1 | Ambient light sensor |
| **BJT** | BC547 / 2N3904 | 1 | Switching transistor |
| **Resistor** | 10 kΩ | 1 | Voltage divider with LDR |
| **Resistor** | 220 Ω | 1 | Current limiting for LED |
| **Potentiometer** | 1 kΩ | 1 | Sensitivity adjustment |
| **LED / Bulb** | 12V | 1 | Output load |

## ⚙️ Working Principle

### Stage 1: Power Supply (220V AC → 12V DC)

The mains 220V AC is first stepped down to 12V AC using a transformer. A bridge rectifier (four 1N4007 diodes) converts the AC to pulsating DC. A 1000 µF smoothing capacitor reduces the voltage ripples, and a 7812 voltage regulator IC provides a stable 12V DC output. An additional 100 µF capacitor provides further filtering.

### Stage 2: Dusk to Dawn Control

The LDR and a 10 kΩ resistor form a voltage divider. In **darkness**, the LDR resistance increases, raising the voltage at the BJT base — the transistor turns ON and current flows through the LED. In **daylight**, LDR resistance drops, the base voltage falls below the threshold, the BJT turns OFF, and the LED switches off. A 1 kΩ potentiometer allows fine-tuning the light sensitivity threshold.

## ✨ Key Features

- **Fully Automatic** — No manual switching; responds to ambient light levels in real-time
- **Two-Stage Design** — Integrated AC-to-DC power supply + light-sensing control circuit
- **Adjustable Sensitivity** — Potentiometer allows tuning the light threshold for different environments
- **Simulation + Hardware** — Verified in both Proteus simulation and breadboard implementation
- **Simple & Cost-Effective** — Built with basic, widely available electronic components

## 🌍 Real-Life Applications

- Automatic street lighting systems
- Garden and outdoor lighting automation
- Energy-efficient lighting control for homes and offices
- Security lighting for residential and commercial spaces

## 📁 Repository Structure

```
Automatic-Dusk-to-Dawn-Light/
│
├── 📄 README.md                                  # Project documentation
└── 📑 Dusk_to_Dawn_Light_Report.pdf              # Lab project report with simulation & hardware photos
```

> **Note:** The PDF report includes the Proteus simulation schematic (page 4), hardware breadboard photo (page 5), and detailed working explanation for both stages.

## 📑 Documentation

| Document | Description |
|----------|-------------|
| [📄 Lab Report (PDF)](Dusk_to_Dawn_Light_Report.pdf) | Full report — circuit design, Proteus simulation, hardware build, working stages, applications |

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| **Proteus** | Circuit simulation and schematic verification |
| **Breadboard** | Hardware prototype implementation |

## 👥 Team

| Name | Student ID | Role |
|------|-----------|------|
| **Ahtisham Saleem** | NIM-BSEE-2021-19 | Circuit Design & Implementation |
| **Muhammad Makki** | NIM-BSEE-2021-23 | Circuit Design & Implementation |


## 📬 Contact

**Ahtisham Saleem**

[![Email](https://img.shields.io/badge/Email-engr.ahtishamsaleem%40gmail.com-red?style=flat-square&logo=gmail)](mailto:engr.ahtishamsaleem@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Ahtisham%20Salim-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/ahtisham-salim)
[![GitHub](https://img.shields.io/badge/GitHub-codebyahtisham-181717?style=flat-square&logo=github)](https://github.com/codebyahtisham)

---

<div align="center">

⭐ **If you found this project useful, consider giving it a star!** ⭐

</div>
