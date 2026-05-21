# AVR128DB48 - AK9723AJ CO₂ Medical Monitoring System

**Embedded real-time CO₂ monitoring system for respiratory waveform analysis using AVR128DB48 MCU and AK9723AJ NDIR sensor.**

<div align="center">

[![AVR](https://img.shields.io/badge/AVR-00979D?style=for-the-badge&logo=arduino&logoColor=white)](https://www.microchip.com/)
[![I2C](https://img.shields.io/badge/I2C-0078D4?style=for-the-badge)](https://en.wikipedia.org/wiki/I%C2%B2C)
[![SPI](https://img.shields.io/badge/SPI-FF6B6B?style=for-the-badge)](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface)
[![UART](https://img.shields.io/badge/UART-115200%20baud-00A86B?style=for-the-badge)](https://en.wikipedia.org/wiki/Universal_asynchronous_receiver-transmitter)
[![DAC](https://img.shields.io/badge/DAC-Analog_Output-8A2BE2?style=for-the-badge)](https://en.wikipedia.org/wiki/Digital-to-analog_converter)
[![Capnography](https://img.shields.io/badge/CO₂-Capnography-red?style=for-the-badge)](https://en.wikipedia.org/wiki/Capnography)

**May 2026 | Jin Yuan Chen**

</div>

---

## System Overview

<p align="center">
  <img src="docs/images/system_block_diagram.png" alt="System Block Diagram" style="max-width:100%; height:auto;"/>
</p>

Real-time embedded platform for **CO₂-based respiratory monitoring (capnography-style waveform generation)**.

The system processes NDIR sensor data and produces both **digital visualization (LCD/UART)** and **analog waveform output (DAC)**.

---

## Core Functionality

- CO₂ concentration measurement (NDIR AK9723AJ via I²C)
- Real-time ppm computation on AVR128DB48
- Respiratory waveform reconstruction via DAC output
- USART terminal interface (115200 baud, interrupt-driven FSM parser)
- SerLCD display output via SPI

---

## System Architecture

| Layer | Implementation |
|------|----------------|
| **Sensor Interface** | AK9723AJ NDIR CO₂ sensor via I²C (TWI) |
| **Processing Core** | AVR128DB48: signal processing + FSM control logic |
| **Output System** | DAC waveform + SerLCD visualization |
| **User Interface** | USART CLI (interrupt-driven command parser) |

---

## Communication Interfaces

| Interface | Role |
|---|---|
| **I²C (TWI)** | Sensor acquisition + calibration control |
| **SPI0** | SerLCD display updates |
| **USART (115200)** | Command-line interface + diagnostics |
| **DAC** | Analog CO₂ waveform output |

---

## Application Domain

- Respiratory monitoring (capnography-style waveform analysis)
- ICU / anesthesia / ventilator feedback systems
- Embedded mixed-signal medical sensing platforms

---

## System Characteristics

- Real-time embedded processing pipeline
- Mixed-signal architecture (digital + analog outputs)
- Interrupt-driven firmware design
- Multi-protocol peripheral integration (I²C, SPI, UART, DAC)
