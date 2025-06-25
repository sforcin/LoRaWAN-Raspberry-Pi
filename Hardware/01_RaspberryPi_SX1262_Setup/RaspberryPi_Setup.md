# SX1262 LoRa Module → Raspberry Pi 5 Wiring Guide

This guide covers the **hardware setup**, **pin mapping**, and **software dependencies** for connecting an **SX1262 LoRa module** to a **Raspberry Pi 5**. This configuration turns your Pi into a mobile LoRaWAN gateway or sensor node.

---

##  Hardware Required

| Component | Details |
|----------|---------|
| Raspberry Pi 5 | Any model with 40-pin GPIO (Pi 3/4 also work) |
| SX1262 Module | e.g., [Waveshare SX1262 LoRa HAT](https://www.waveshare.com/wiki/SX1262_LoRa_HAT) |
| Jumper Wires | Female-to-female |
| Optional: Breadboard | For prototyping convenience |

---

##  Power Notes

- The SX1262 operates at **3.3V**.
- DO NOT connect to 5V — this may damage the LoRa module (Which has happened in this project)
- The Pi 5 has a dedicated **3.3V rail** on Pin 1 or Pin 17.

---

##  Wiring Table (SX1262 ↔ Raspberry Pi 5)

| SX1262 Pin | Pi GPIO Pin | BCM Pin | Notes |
|------------|-------------|---------|-------|
| **VCC**    | Pin 1       | 3.3V    | Power input |
| **GND**    | Pin 6       | GND     | Ground |
| **SCK**    | Pin 23      | GPIO11  | SPI Clock |
| **MISO**   | Pin 21      | GPIO9   | SPI MISO |
| **MOSI**   | Pin 19      | GPIO10  | SPI MOSI |
| **NSS**    | Pin 24      | GPIO8   | Chip Select (CE0) |
| **RESET**  | Pin 15      | GPIO22  | Required |
| **BUSY**   | Pin 13      | GPIO27  | Required |
| **DIO1**   | Pin 16      | GPIO23  | Interrupt pin |

> Use consistent 3.3V logic level — **no level shifters needed** between Pi and SX1262.

---

## GPIO Pinout Reference

```plaintext
Pi 5 GPIO (top view)

(3.3V) 1  ● ● 2  (5V)
(GPIO2) 3  ● ● 4  (5V)
(GPIO3) 5  ● ● 6  GND
(GPIO4) 7  ● ● 8  (GPIO14)
( GND ) 9  ● ● 10 (GPIO15)
(GPIO17)11 ● ● 12 (GPIO18)
(GPIO27)13 ● ● 14 GND
(GPIO22)15 ● ● 16 (GPIO23)
(3.3V)17 ● ● 18 (GPIO24)
(GPIO10)19 ● ● 20 GND
(GPIO9) 21 ● ● 22 (GPIO25)
(GPIO11)23 ● ● 24 (GPIO8)
( GND )25 ● ● 26 (GPIO7)
