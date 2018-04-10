# PIC Serial Bootloader
This is a serial bootloader originally written for the **PIC18F66K22** MCU.  The base bootloader has been provided by Microchip under the AN1310 engineering application.  

# Architecture
The Panel Interface Processor (PIP) is the **PIC18F66K22**.  Serial communication is achieved via an FTDI Serial-to-USB converter (**FT232RL**). MCU serial pins utilized are pins 31 (MCU TX), and 32 (MCU RX).    

# Dependencies
* IDE and version: MPLAB X v3.45
* Compiler and version: mpasmx v5.48
* Linker and version: mplink v4.46
* PIC18 Bootloader.asm
* bootconfig.inc
* devices.inc
* preprocess.inc

# Tagged Versions 
"Out of the box", the bootloader was sitting at revision v1.6.  Other tagged versions were not well documented, nor was there strict use of a revision control system.    

* Revision v2.0 -- Bootload BAUD rate hardcoded at 115200bps.  Bootloader size adjusted accordingly.  Bootloader resides at the beginning of program space, thus reset/interrupt vectors have been remapped.  