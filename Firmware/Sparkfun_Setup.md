# Setup Guide for SparkFun SAMD21 Pro RF

## Components: 
* SparkFun SAMD21 Pro RF
* MacBook
* micro USB - USB-C Cable

## Setup Instructions
1. Connect board to computer (Pwr light should turn on)
2. In terminal, run "ls /dev/tty.*"
3. Download Arduino IDE
4. Go to preferences, additional board URL, paste this : https://raw.githubusercontent.com/sparkfun/Arduino_Boards/main/IDE_Board_Manager/package_sparkfun_index.json
5. Go to Tools > Board > Boards Manager and install: SparkFun SAMD Boards
6. Then select: Board: SparkFun SAMD21 Pro RF -> Port: The one you found earlier (e.g. /dev/cu.usbmodemXYZ1)
7. Go to File > Examples > SparkFun LoRaSerial (if available), or install the RadioHead or LoRa library.
8. Try the example LoRaSerialExample or LoRaSender to test basic transmission
9. To try each file, verify and then upload it
10. When changes are made to the board itself, using the computer's port, the lights on the board should blink


* Make sure to run codes one by one, and do not overload the board, otherwise it will go into bootloading mode, and you will need the debugger to get it out of that state
