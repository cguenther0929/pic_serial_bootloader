# PIC Serial Bootloader
This is a serial bootloader originally written for the **PIC18F66K22** MCU.  The base bootloader has been provided by Microchip under the AN1310 engineering application.  At the time of writing this, the best set of instructions for how to implement and use the bootloader can be found under the PTE production documentation set.  It's critical to note that the application being loaded get an offset of 0x800 to avoid clobbering the bootloader which 'lives' at the beginning of program space. For instructions on how to apply a code offset, see the README file in the repository for the application to be bootloaded.   

# Architecture
The Panel Interface Processor (PIP) is the **PIC18F66K22**.  Serial communication is achieved via an FTDI Serial-to-USB converter (**FT232RL**). MCU serial pins utilized are pins 31 (MCU TX), and 32 (MCU RX).    

# Dependencies
* IDE and version: MPLAB X v5.10
* Compiler and version: mpasmx v5.82
* Linker and version: mplink v5.09
* PIC18 Bootloader.asm
* bootconfig.inc
* devices.inc
* preprocess.inc

# Tagged Versions 
"Out of the box", the bootloader was sitting at revision v1.6.  Other tagged versions were not thoroughly documented, nor was a revision control system utilized.  

* Revision v2.0 -- Bootload BAUD rate hardcoded at 115200bps.  Bootloader size adjusted accordingly.  Bootloader resides at the beginning of program space, thus reset/interrupt vectors have been remapped.  

* Revision v2.1 -- Simply updated .gitignore file.