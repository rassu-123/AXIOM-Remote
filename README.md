# AXIOM Remote

## Description

A universal remote control with buttons, dials and an LCD for menu/settings (no live video) for AXIOM devices and potentially many other things as well.

## Build status

| master | dev |
|:------:|:------:|
|[![CircleCI](https://circleci.com/gh/apertus-open-source-cinema/AXIOM-Remote/tree/master.svg?style=svg)](https://circleci.com/gh/apertus-open-source-cinema/AXIOM-Remote/tree/master)|[![CircleCI](https://circleci.com/gh/apertus-open-source-cinema/AXIOM-Remote/tree/dev.svg?style=svg)](https://circleci.com/gh/apertus-open-source-cinema/AXIOM-Remote/tree/dev)|

## Build instructions

### Bootloader

- Open **Bootloader** folder in terminal
- Execute **make** or when rebuilding **make clean && make**
- **HEX** and **ELF** files would placed in the **build** folder
- After flashing connect with **minicom** and reset the board, after a short moment the information about west key manager will be shown

### Firmware

- Open **Firmware** folder in terminal
- Execute **make** or when rebuilding **make clean && make**
- **HEX** and **ELF** files would placed in the **build** folder

## Flash instructions
Note that with the current hardware the PICKit2 needs to stay connected for normal operation even when flashing has been completed as the PICkit2 pulls down the RESET signal.

### IPE

- Open IPE and connect to your PICKit3 or later, drag and drop the HEX file into the IPE window
- Click **Program**, after a moment it should be finished and main menu with 6 buttons shown

### pic32prog

- Acquire binary or build from source from: https://github.com/sergev/pic32prog to flash with PICKit2
- run **sudo ./pic32prog yourfile.hex** and you should see a progress bar of the flashing/verification process

## Usage instructions

### Firmware
- USB communication to/from the AXIOM Remote is done via a USB communications device class (CDC)
- **sudo minicom -D /dev/ttyACM0** (baud rate is not required)
