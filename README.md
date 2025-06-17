# USDA Drone-Mounted LoRaWAN Gateway Research

> **Project under the USDA Digital Agriculture Fellowship - University of California, Riverside (Department of Electrical and Computer Engineering)**

---

## 🔭 Project Vision

The objective of this research project is to develop a mobile, drone-mounted LoRaWAN gateway that autonomously collects data from distributed LoRa-enabled sensors in agricultural fields and relays this data to cloud platforms for further analysis.

By combining autonomous flight with long-range low-power communication (LoRa), this system aims to address the challenges of data loss in traditional static gateways, improve data collection efficiency, and increase the scalability of IoT deployments in precision agriculture.

---

## 🌾 Project Overview

In modern agriculture, real-time environmental data is essential for optimizing water usage, improving crop growth, and enhancing sustainability. Traditional LoRaWAN networks rely on stationary gateways, but these can suffer from:

- Line-of-sight issues
- Terrain obstructions
- Limited coverage in large fields

Our system utilizes a drone-mounted LoRaWAN gateway capable of dynamically positioning itself over sensor nodes to maximize communication range and minimize data loss. After collection, data is transmitted to a base station and uploaded to The Things Network (TTN) for cloud-based processing and analysis.

---

## ⚙️ System Components

### Hardware

- **Mobile Gateway (Drone-Based)**
  - 3DR SOLO Drone (modified)
  - Raspberry Pi 5
  - SX1262 LoRa HAT (850-915 MHz)
  - Portable battery system
  - Lightweight custom mounting system
  - Soil moisture sensors (SE01-LS, SDI-12-LS for testing)

- **Alternative Hardware Setups**
  - Arduino + SX1262 module (alternative configuration)
  - SparkFun SAMD21 Pro RF (alternative MCU-based solution)

- **Ground Base Station**
  - Receives data from drone gateway
  - Acts as intermediary to The Things Network

- **Cloud Platform**
  - The Things Network (TTN) integration for real-time data upload

---

## 🚧 Current Progress

- ✅ Developed multiple hardware configurations for LoRaWAN gateway:
  - Raspberry Pi 5 with SX1262 LoRa HAT
  - Arduino with SX1262 modules
  - SparkFun SAMD21 Pro RF with J-Link debugger
- ✅ Configured Raspberry Pi OS for remote SSH access and development.
- ✅ Mounted hardware on 3DR SOLO drone.
- ✅ Registered gateway with The Things Network.
- ✅ Developed initial Python LoRa communication scripts.
- ✅ Started transition to LPIO GPIO libraries for Raspberry Pi 5 compatibility.
- ✅ Conducted initial field testing of drone-mounted system.
- ✅ Integrated and tested soil moisture sensors.
- ✅ Documented hardware setups and wiring for all configurations.

---

## 🐞 Current Technical Challenges

- Magnetic interference errors when mounting antennas and batteries on drone.
- Inconsistent TTN packet reception due to limited documentation.
- Raspberry Pi 5 GPIO deprecated — requiring GPIO software adaptation.
- SAMD21 bootloader recovery and SWD debugging required via J-Link.
- Live packet capture and field deployment tests still under ongoing development.

---

## 📁 Repository Structure

- `/Hardware/` – Detailed hardware setups for Raspberry Pi, Arduino, and SparkFun SAMD21 configurations.
- `/Firmware/` – Code for Raspberry Pi (Python), Arduino, and SAMD21 boards.
- `/System_Design/` – Diagrams of system architecture, deployment flow, and data pipeline.
- `/Field_Tests/` – Drone flight tests, signal strength logs, and deployment notes.
- `/Documentation/` – USDA progress reports, references, and technical notes.
- `/Challenges_and_Debugging/` – Full logs of technical obstacles encountered and solutions.

---

## 📅 Next Steps (2024-2025)

- Finalize stable drone-mounted flight profile with reduced interference.
- Complete transition to LPIO for Raspberry Pi GPIO support.
- Expand TTN integration for consistent cloud data upload.
- Begin full-scale field testing for multi-node deployment.
- Build real-time data visualization tools for research.

---

> **This repository is a living document and will be continuously updated as the project progresses.**

