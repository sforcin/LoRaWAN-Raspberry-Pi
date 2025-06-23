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

Part 2: 
1. Go to Tools > Board > Boards Manager
2. In the search bar, type: SparkFun SAMD
3. SparkFun SAMD Boards
4. select Board: SparkFun SAMD21 Pro RF
5. Tools > Port → select /dev/cu.usbmodem2101

output: 
Downloading packages
arduino:arm-none-eabi-gcc@7-2017q4
arduino:bossac@1.8.0-48-gb176eee
arduino:openocd@0.9.0-arduino
arduino:CMSIS@4.5.0
arduino:CMSIS-Atmel@1.2.0
SparkFun:samd@1.8.13
Installing arduino:arm-none-eabi-gcc@7-2017q4
Configuring tool.
arduino:arm-none-eabi-gcc@7-2017q4 installed
Installing arduino:bossac@1.8.0-48-gb176eee
Configuring tool.
arduino:bossac@1.8.0-48-gb176eee installed
Installing arduino:openocd@0.9.0-arduino
Configuring tool.
arduino:openocd@0.9.0-arduino installed
Installing arduino:CMSIS@4.5.0
Configuring tool.
arduino:CMSIS@4.5.0 installed
Installing arduino:CMSIS-Atmel@1.2.0
Configuring tool.
arduino:CMSIS-Atmel@1.2.0 installed
Installing platform SparkFun:samd@1.8.13
Configuring platform.
Platform SparkFun:samd@1.8.13 installed


 * Try the example LoRaSerialExample or LoRaSender to test basic transmission
 * To try each file, verify and then upload it
 * When changes are made to the board itself, using the computer's port, the lights on the board should blink


* Make sure to run codes one by one, and do not overload the board, otherwise it will go into bootloading mode, and you will need the debugger to get it out of that state



