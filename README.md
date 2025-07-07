# USDA Drone-Mounted LoRaWAN Gateway Research

> **Project under the USDA Digital Agriculture Fellowship - University of California, Riverside (Department of Electrical and Computer Engineering)**

---

##  Project Vision

The objective of this research project is to develop a mobile, drone-mounted LoRaWAN gateway that autonomously collects data from distributed LoRa-enabled sensors in agricultural fields and relays this data to cloud platforms for further analysis.

By combining autonomous flight with long-range low-power communication (LoRa), this system aims to address the challenges of data loss in traditional static gateways, improve data collection efficiency, and increase the scalability of IoT deployments in precision agriculture.

---

## Project Overview

In modern agriculture, real-time environmental data is essential for optimizing water usage, improving crop growth, and enhancing sustainability. Traditional LoRaWAN networks rely on stationary gateways, but these can suffer from:

- Line-of-sight issues
- Terrain obstructions
- Limited coverage in large fields

Our system utilizes a drone-mounted LoRaWAN gateway capable of dynamically positioning itself over sensor nodes to maximize communication range and minimize data loss. After collection, data is transmitted to a base station and uploaded to The Things Network (TTN) for cloud-based processing and analysis.

---

##  System Components

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

##  Current Progress
I was able to make my setup work with the Sparkfun Pro RF, and while flashing arduino code with it, receive messages that the node is transmitting and receiving signals successfully

---

##  Current Technical Challenges
Despite the challenge of making the gateway work with the power supply due to interference,we also need to ensure the drone collects all the data needed. I have files with specific issues and debugging options for both setups I attempted for this system.



---

## Next Steps 
- Test the setup with real sensors on the field
- Connect all the sensors into a network of sensors using TTN
- Once the network of sensors is created, run tests to make sure the data is being collected properly
- Write algorithms to process data and create graphs from it
- Improve data packet transfers if needed

---

## Project Conclusion
- As a latest update, I attempted to recover the SAMD21 using the debugger, but something went wrong along the process.
- I have uploaded all code I found and used in order to attempt this project.

> **This repository is a living document and will be continuously updated as the project progresses.**

