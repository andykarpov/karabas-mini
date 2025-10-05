# Karabas Go Mini How-to

How to prepare the newly created devboard to run:

1. Prepare an SD card #1 with cores (*.kg2 for rev.C-F3 or *.kg3 for rev.G) and joystick drivers (drivers directory with ini files) in the root of SD card. The SD card could be FAT16, FAT32 or EXFAT formatted.

2. Upload the RP2040 firmware:

- Press and hold the "RP Boot" button
- Press then release the "RP Reset" button
- Release the "RP Boot" button
- Put the firmware.uf2 (for rev.C - rev.F3) or firmware_g.uf2 (for rev.G) into a mounted drive
- Wait a bit until it reboots
- Done, the boot.kg2 on rev.C-rev.F3 or boot.kg3 on rev.G core should starts

3. Profit

