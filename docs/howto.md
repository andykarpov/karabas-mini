# Karabas Go Mini How-to

How to prepare the newly created devboard to run:

1. Prepare an SD card #1 with cores (*.kg2 for rev.C-F3 or *.kg3 for rev.G) and joystick drivers (drivers directory with ini files) in the root of SD card. The SD card should be FAT32 formatted.

2. Upload the RP2040 firmware:

- Press and hold the "RP Boot" button
- Press then release the "RP Reset" button
- Release the "RP Boot" button
- Put the firmware.uf2 (for rev.C - rev.F3) or firmware_g.uf2 renamed to firmware.uf2 (for rev.G) into a mounted drive
- Wait a bit until it reboots
- Done, the boot.kg2 on rev.C-rev.F3 or boot.kg3 on rev.G core should starts
- Please read the manual of each core what to place on SD2 for each of them

3. Upload the ESP32-S3 firmware:

- Close jumper JP11
- Power the main board with USB-C
- Connect a secondary USB-C cable to the upper board
- edit (change the com port address) and run the flash.bat (or flash.sh)
- after successful flashing, remove the JP11 jumper, disconnect both USB-C cables

