# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

The release repo of the Karabas Mini and Mini G boards (Xilinx Spartan-6 XC6SLX25, RP2040 MCU, FT812, HDMI/DVI, ESP8266, an ESP32-S3 on the shield): what goes onto the SD card and the board, plus the hardware documents. There is no source code and nothing to build here. The cores are built in their own repos (`karabas-go-core-*`), the MCU firmware in `karabas-go-firmware`, the PCB sources in `karabas-mini-pcb`. The hardware design and docs are CC BY-NC-SA 4.0 (`LICENSE`); cores and firmware have their own licenses.

Two board families: Rev.C .. Rev.F3 take `firmware.uf2`, Rev.G / G2 `firmware_g.uf2` (renamed to `firmware.uf2` when copied to the board); the cores are the same files for both, `docs/howto.md`. Rev.C, D and F need the hardware mod of `revF_mod.md` (the FT812 clock from the FPGA on MCU_IO4 instead of the crystal) for the cores that use the FT812 (boot, tsconf).

## Layout

- No `cores/`: the cores of all the boards are `.kg` files in the sibling repo `karabas-go` (`cores/`, `boot.kg` is the boot menu); README.md says so. The cores are `.kg` files: one file for Go, Mini and Mini G (format kgo2, karabas-go-tools `docs/kgo2.md`); they need the firmware 26110415 or later (`firmware/`), an older firmware does not see them and stops with "Boot file not found". They go into the root of SD card 1.
- `firmware/firmware.uf2` (Mini), `firmware/firmware_g.uf2` (Mini G): the RP2040 firmware, copied to the `RPI-RP2` drive in BOOTSEL.
- `firmware/esp32-s3/`: the ESP32-S3 firmware of the shield (`bootloader.bin`, `partition-table.bin`, `esp-spi.bin`) and `flash.sh` / `flash.bat` (esptool, edit the port first; JP11 closed while flashing). `firmware/esp32-s3-old-zifi/`: the older ZiFi build with `zifi.spg`.
- `software/`: extra files for the cores (`TBBLUE.FW` of ZX Next, `.WMF` plugins, `gopher_esp32.spg`).
- `docs/`: `howto.md` (first start), the schematics (`karabas-mini-rev*.pdf`) and interactive BOMs (`*-ibom.html`) of each revision and shield, the renders used by `README.md`.
- `pcb/`: the gerbers of each board revision and shield. `PCB_CHANGELOG.md`: the revisions (latest stable Rev.G, then G2).
- `case/`: 3D enclosure models (STL, 3MF), one dir per shield stack.

## Release

- `firmware/firmware.uf2` and `firmware/firmware_g.uf2` are committed by the CI release job of `karabas-go-firmware` (`.github/workflows/build.yml`, the `SIBLING_REPOS_TOKEN` secret, commits "Firmware build <version>: ..." by github-actions[bot]). Never commit them by hand. The job also removes `cores/karabas.ini`, `firmware/karabas.ini` and `firmware/drivers` if they appear. The ESP32-S3 files are not touched by the job.
- Core releases go to `karabas-go` only (`cores/*.kg`).
- The CI job pushes with `git pull --rebase`: pull before committing a core, the firmware may have moved on.
- Commit only the files of the release. Do not commit untracked user files (local `karabas.ini`, drivers, test images).
- Do not touch `case/`, `pcb/` and the PCB documents unless asked: they come from the hardware work, not from the cores or the firmware.

## Memory

The Claude Code memory of this repo is shared with all karabas-go repos: `~/.claude/projects/<this project>/memory` is a symlink to `../../karabas-go/karabas-go-notes` (private repo `andykarpov/karabas-go-notes`, `link.sh` there makes the links). Its `MEMORY.md` is split by repo; commit and push it after every memory change.
