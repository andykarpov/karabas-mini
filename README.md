# Karabas-Go Mini

A Spartan-6 based devboard to emulate different retro-computers.

[![Creative Commons License](https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc-sa/4.0/)

The hardware design and documentation are licensed under [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International](http://creativecommons.org/licenses/by-nc-sa/4.0/).

FPGA cores, the firmware and other software parts are licensed by their own licenses.

### What's on the board:

- A 25k LE's Spartan-6 FPGA
- RP2040 MCU
- 4x USB Ports
- 2x 2MB 10ns SRAM chips
- 32MB SDRAM chip
- DVI output
- On-board FT812 video processor
- SAM2695 midi synth
- 2x microSD cards
- Tape In/Out interface
- DS3221 RTC
- 1kB EEPROM
- ESP8266 Wi-Fi module
- uBUS expansion connector

### PCB 

The latest stable PCB revision number is Rev.F3.

The latest development PCB revision number is Rev.G.

### Pre-production renders:

![image](https://github.com/andykarpov/karabas-mini/blob/master/docs/karabas-mini-top.png?raw=true)

![image](https://github.com/andykarpov/karabas-mini/blob/master/docs/karabas-mini-bot.png?raw=true)

### Required HW mod for all revisions before Rev.G:

The latest cores that uses FT812 chip (boot and tsconf) now requires a generated clock by FPGA instead of 8MHz crystal oscillator.
To perform the mod please do the following:

1. Remove the crystal Y3 (8 MHz)
2. Remove capacitors C40, C41 (18 pF)
3. Find a FPGA net MCU_IO4 and connect it to the Y3 pin 1 by a thin wire

<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/6c0353e9-72ee-4333-b9af-bc0b21796d64" />

<img width="859" height="707" alt="image" src="https://github.com/user-attachments/assets/598732b1-598a-4d0c-96e7-f6a9aea87d72" />

