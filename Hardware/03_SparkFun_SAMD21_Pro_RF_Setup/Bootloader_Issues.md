#  Bootloader Recovery – SparkFun SAMD21 Pro RF

This guide explains how to recover the **SparkFun SAMD21 Pro RF** if it enters bootloader mode, stops responding to uploads, or appears to be “bricked.” These issues are often caused by:
- Crashes during upload
- Flooding Serial too quickly
- Incorrect board or port settings

---

##  Common Bootloader Symptoms

| Symptom | Meaning |
|--------|---------|
| Board not detected in Arduino IDE | MCU may be stuck in bootloader or USB stack crash |
| Constant or no LED blinking | Board stuck in a loop or failed upload |
| Upload fails without progress | USB device not enumerating or wrong board setting |
| Upload only works after RESET | Bootloader only accepts uploads in DFU window |

---

##  Safe Upload Strategy (To Prevent Bootloader Lock)

1. Use this template for safe startup (in arduino IDE software)
    ```cpp
    void setup() {
      Serial.begin(9600);
      delay(1000); // Allow USB to settle
      Serial.println("Board is alive");
    }

    void loop() {}
    ```


---

## 
How to Recover from Bootloader Lock

### Option 1: Double-Tap RESET

1. Quickly press the **RESET button twice**.
2. The **yellow LED** should start pulsing → bootloader mode is active.
3. In Arduino IDE:
   - Select `Adafruit Feather M0` as the board (for SAMD21)
   - Re-select the **new COM port** that appears
   - Re-upload your sketch
  
  * This did not work with mine. if you do this, ensure you are only clicking the reset button once, and that the board is still functional after, if it is not, you must proceed to option 2

---

### Option 2: Flash Bootloader via J-Link (Advanced)

1. Requires: [SEGGER J-Link EDU Mini](https://www.segger.com/products/debug-probes/j-link/models/j-link-edu-mini/)
2. Connect SWDIO, SWCLK, GND, and VREF to the J-Link header
3. Use SEGGER J-Flash or `openocd` to re-flash the SparkFun bootloader

> Download bootloader here:  
>  [SparkFun SAMD21 Pro RF GitHub - Bootloader](https://github.com/sparkfun/Arduino_Boards/tree/main/sparkfun/samd/bootloaders)
* Notes:
-    if you do this, make sure it is only for educational purposes. The debugger CANNOT be used for industrial or professional purposes
-    Also, make sure you have a stable connection between the jumper wires is secure, you may also solder if you know how to
---


