#  SX1262 Issues + Troubleshooting

This document outlines common issues encountered when working with the SX1262 LoRa module (especially in Raspberry Pi and Arduino/SAMD21 setups), and how to fix them.

---

## Issues I have faced, and how I attempted to solve them

###  **SX1262 init failed**

**Cause:**  
The module cannot initialize — usually due to incorrect wiring or missing control pins.

**Fix:**
- Double-check `RESET`, `BUSY`, and `DIO1` pins are connected to GPIOs.
- Ensure you're using **3.3V** (not 5V).
- NSS (chip select) must be properly defined in code.
- Make sure you are using the correct frequency (915 Hz for USA)
- Double check wiring diagram for raspberry pi and chip

---

###  2. **No packets received / RX always empty**

**Cause:**  
Receiver is initialized but never detects incoming LoRa packets.

**Fix:**
- Ensure both sender and receiver use **the same frequency** (e.g., 915 MHz).
- Check spreading factor, bandwidth, and coding rate match on both ends.
- Use an **antenna** — SX1262 performs poorly without one.
- Confirm `DIO1` is wired correctly (used for RX_DONE interrupt).
- Connect Antenna to Raspberry Pi
- Write debugging code in receiver.py code to output frequencies it's checking, and what is going on under the hood
- * These helped me realize that my code was actually looking for the frequencies, but that was not where the issue was

---

###  3. **SPI hangs / timeout / busy stuck**

**Cause:**  
The `BUSY` pin is not responding correctly.

**Fix:**
- `BUSY` must be wired and declared in the code.
- Never omit `BUSY` or the device will hang on SPI commands.
- Check with a logic analyzer or serial print if the system halts at `begin()`.
- i was not able to fix this issue in my setup, so these are tentative !

---

###  4. **Continuous RESET loop / crashing**

**Cause:**  
Improper voltage levels or excessive draw from Pi.

**Fix:**
- Use external regulated 3.3V power if needed.
- Use short jumper wires to minimize voltage drop.
- Ensure RESET pin is not floating — tie it to a GPIO and pull HIGH at setup.

---


##  Debug Tips

| Tool | Purpose |
|------|---------|
| Serial Monitor | Check output for “init failed” or packet logs |
| `digitalRead()` | Verify `BUSY`, `RESET`, `DIO1` logic levels |
| Logic Analyzer | Track SPI transactions |
| Multimeter | Confirm 3.3V power rail on VCC |

---

## Debugging Toolkit

- [ ] SPI enabled (Raspberry Pi: `raspi-config`)
- [ ] 3.3V power supply confirmed
- [ ] RESET, BUSY, DIO1 wired
- [ ] SPI (MOSI/MISO/SCK/NSS) connected properly
- [ ] Antenna connected
- [ ] Frequency matches other LoRa nodes (915 MHz)
- [ ] Library used: [SX126x-Arduino](https://github.com/beegee-tokyo/SX126x-Arduino)

---

For deeper debugging, refer to:  
 [BeeGee SX126x-Arduino Issues](https://github.com/beegee-tokyo/SX126x-Arduino/issues)

