# LoRaWAN-Raspberry-Pi
This repository contains the project specifications and setup instructions for building a mobile LoRaWAN Gateway using a Raspberry Pi 5 and an SX1262 LoRa HAT. This gateway is mounted on a DJI Mini Pro 4 drone to collect data from LoRa-enabled sensors across large agricultural fields.

This project is part of the USDA Digital Agriculture Fellowship, in collaboration with the University of California, Riverside, Department of Electrical and Computer Engineering.

**Project Overview**

In modern agriculture, sensor-based monitoring systems are essential for optimizing water usage, improving crop growth, and increasing efficiency. However, traditional LoRaWAN setups rely on stationary gateways, which can result in data loss over long distances or in non-line-of-sight conditions. To address this, we have developed a mobile LoRaWAN gateway mounted on a drone, allowing dynamic positioning to ensure reliable data collection from sensors over vast areas. This system offers better coverage, reduces data loss, and can significantly improve the scalability of IoT deployments in agriculture.


**Hardware List**
(add links)
- Raspberry Pi 5
- SX1262 LoRa HAT
- DJI Mini Pro 4 Drone
- Portable Lightweight Battery
- Velcro Straps for Mounting
- GPIO Jumper Cables
- SE01-LS and SDI-12-LS Soil Moisture Sensors (for testing)
- Ethernet Cable
- The following are **optional**, in case you want to use a monitor with keyboard and mouse
- Raspberry PI HDMI Adapter for HDMI
- HDMI Cable
- Keyboard and mouse


**Setup Instructions**

Step 1: Raspberry Pi Setup
Flash the Raspberry Pi OS onto the microSD card using Raspberry Pi Imager (add link)
  - If you are going to use an adapter for the microSD, make sure you are installing the OS on the microSD, not the adapter. 
  - When downloading the Raspberry Pi OS, make sure you enable ssh, and choose easy login and password.
  - Also, just download the recommended OS. 
Insert the microSD card into the Raspberry Pi and power it up, connect 
  - It is recommended to use a power outlet, instead of connecting it to a computer or a phone.
Connect to the Raspberry Pi via SSH:
  - If you have admin access to your router, you could login and find the IP address of the Raspberry pi, or:
  - Download Angry IP Scanner on a computer, and run IP scan to find all devices connected to your network.
  - After finding the IP address of the Raspberry Pi, copy that.
  - Open your terminal, and run the command ssh [username]@IP_ADDRESS
  - Type your password, press enter. You should see your username in green if successfully connected
Install the required libraries for LoRa communication:
```bash
sudo apt update
sudo apt install python3-pip
pip3 install lora-python-lib
```

Step 2: LoRa HAT Setup
Attach the SX1262 LoRa HAT onto the Raspberry Pi GPIO pins as per the manufacturer's documentation.
  - In my case, I attached the LoRa using jumper cables (female to male), but maybe it is different for your model of the module.
  - Connect the jumper cables to ensure stable communication between the Pi and the HAT.
  - If the light on the module is blinking, or solid red, it means the module was successfully connected.



