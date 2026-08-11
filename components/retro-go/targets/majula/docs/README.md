Majula V2.1 ESP32-P4 handheld game console.

Networking has not been tested yet, so build the image without it:

command to build: `python rg_tool.py --target majula build-img --no-networking`

ESP-IDF v5.5 is recommended.

## ESP32-P4
- Status: development target

## Hardware
- Board: Majula V2.1 (custom ESP32-P4 handheld)
- MCU: ESP32-P4 (WT0132P4-A1 module, 82 pins)
- Display: ST7701 MIPI DSI (1-lane), 480x640 portrait / 640x480 landscape
- SD card over SDMMC (4 bits)
- NS4168 I2S audio amplifier
- TP4056 Li-ion battery charger
- GEK100-00 power management IC (soft power on/off)
- USB-C (16P) for charging and data
- 16 buttons (D-pad, A/B/X/Y, L/R, Start/Select, Menu, Option, Vol+/-)

## Pin Assignments (from Altium schematic P1.schdoc V2.1)

### Display (MIPI DSI)
- DSI_CLK+/- : ESP32-P4 dedicated DSI pins
- DSI_DATA0+/- : ESP32-P4 dedicated DSI pins
- LCD_RST  : GPIO23
- LCD_BCKL : GPIO5

### SD Card (SDMMC 4-bit)
- CLK : GPIO43
- CMD : GPIO44
- D0  : GPIO39
- D1  : GPIO40
- D2  : GPIO41
- D3  : GPIO42

### Audio (I2S -> NS4168)
- I2S_BCK  : GPIO7
- I2S_WS   : GPIO8
- I2S_DATA : GPIO6
- AMP_CTRL : GPIO9

### Buttons (GPIO, active LOW with pull-up)
- LEFT   : GPIO20
- RIGHT  : GPIO18
- UP     : GPIO17
- DOWN   : GPIO19
- SELECT : GPIO21
- START  : GPIO10
- MENU   : GPIO15
- OPTION : GPIO16
- A      : GPIO14
- B      : GPIO13
- X      : GPIO12
- Y      : GPIO11
- L      : GPIO1
- R      : GPIO0
- VOL+   : GPIO34 (not mapped to gamepad)
- VOL-/BOOT : GPIO35 (not mapped to gamepad, also boot button)

### Battery
- VBAT_VOLTAGE : GPIO22 (ADC1_CH6)

### USB
- USB_DM/DP : ESP32-P4 dedicated USB pins
