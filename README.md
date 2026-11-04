# Karabas-Go Mini

A Spartan-6 based devboard to emulate different retro-computers.

[![Creative Commons License](https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc-sa/4.0/)

The hardware design and documentation are licensed under [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International](http://creativecommons.org/licenses/by-nc-sa/4.0/).

FPGA cores, the firmware and other software parts are licensed by their own licenses.

### Cores

The cores are in the [karabas-go](https://github.com/andykarpov/karabas-go) repository now, `cores/`: one `.kg` file per core for every board (Karabas Go, Mini and Mini G). Copy them to the root of SD card #1. They need the firmware 26110415 or later (`firmware/` of this repo: `firmware.uf2` for rev.C - rev.F3, `firmware_g.uf2` for rev.G / G2); an older firmware does not see `.kg` files and stops with "Boot file not found". The old `.kg2` / `.kg3` files are gone.

Ядра теперь лежат в репозитории [karabas-go](https://github.com/andykarpov/karabas-go), каталог `cores/`: один файл `.kg` на ядро для всех плат (Karabas Go, Mini и Mini G). Их нужно скопировать в корень SD-карты #1. Нужна прошивка 26110415 или новее (`firmware/` этого репозитория: `firmware.uf2` для rev.C - rev.F3, `firmware_g.uf2` для rev.G / G2); старая прошивка не видит файлы `.kg` и останавливается с «Boot file not found». Старых файлов `.kg2` / `.kg3` больше нет.

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
- ESP32-S3 as VDAC32 mcu
- CF card

### PCB 

The latest stable PCB revision number is Rev.G.

Warning: RevC,D,F requires a small [HW mod](https://github.com/andykarpov/karabas-mini/blob/master/revF_mod.md)

PCB source project: https://github.com/andykarpov/karabas-mini-pcb

### Pre-production renders:

![image](https://github.com/andykarpov/karabas-mini/blob/master/docs/karabas-mini-top.png?raw=true)

![image](https://github.com/andykarpov/karabas-mini/blob/master/docs/karabas-mini-bot.png?raw=true)

### Shield with CF card and ESP32-S3 for rev.G (2nd floor)

![image](https://github.com/andykarpov/karabas-mini/blob/master/docs/karabas-mini-shield-v4-top.png?raw=true)

![image](https://github.com/andykarpov/karabas-mini/blob/master/docs/karabas-mini-shield-v4-bot.png?raw=true)

### Shield for v4 shield with Dot matrix display (3rd floor)

![image](https://github.com/andykarpov/karabas-mini/blob/master/docs/karabas-mini-shield-v4-disp-top.png?raw=true)

![image](https://github.com/andykarpov/karabas-mini/blob/master/docs/karabas-mini-shield-v4-disp-bot.png?raw=true)



