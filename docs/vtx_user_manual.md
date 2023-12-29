# User Manual

## Power

Different VTXs have different power requirements, please refer to the **target** for detial.

## Led

All VTXex have two LEDs

### RED LED

power indicator light. 

The VTX lights up when powered on and goes off when powered off. It will not flash.

### BLUE LED

Working status indicator light.

- flicker 3x after boot indicates MSP signaling is detected.
- OFF = camera lost (check camera and cabling)
- ON/OFF @ 1hz = heat protection
- ON/OFF @ 4hz = 0MW pitt mode active
- ON/OFF @ 2hz = 0.1mw pitt mode active
- Flashes quickly 2 times per second = RF chip(dm6300) failure
- ON solid = VTX operation normal

## Keypad

Note not all VTXes support keypad.

<img src="https://raw.githubusercontent.com/ligenxxxx/hdzero-vtx-docs/main/site/img/Keypad_Usage.png" style="width:100">

## UART

- VTX is connected to FC through UART to implement OSD and other functions that require remote control cooperation.
- Do not use soft serial uart.
- VTX TX <=> FC RX
- VTX RX <=> FC TX

## OSD setup

### Prerequisition

- Betaflight >= v4.4.0
- iNav >= 4.1.0
- FlightOne >= 10.1.1.5576 | 10.1 Alpha 29

### Update VTX and VRX/Goggle firmware

- Download the latest firmware from [www.hd-zero.com/document](www.hd-zero.com/document).
- Firmware package(Rev_ddmmyyyy.zip) contains the firmware for all the VTX and VRX/Goggle.
- You can also get the latest release fw of vtx and goggle from github.

### Solder/Connect UART to and available on your FC board

See **UART** abve.

### Flight Controller Configuration(Use betaflight as example)

- Connect the FC board to computer with an USB cable
- Start Betaflight Configurator
- Go to Port TAB
- Activite VTX (MSP + Displayport) on UART number that is used to connect the VTX
- Save and Reboot

**Note:** A soft UART is *not* supported for VTX (MSP + Displayport).

As an example: UART3 on picture below is used for VTX (MSP + Displayport).

<img src="https://raw.githubusercontent.com/ligenxxxx/hdzero-vtx-docs/main/site/img/Betaflight_port_config.png" style="width:100">

## VTX Table

You really don't need to care about it because VTX will automatically configure the vtx table of the FC.

## Stick Command

Before using stick command, make sure that fc uart is set correctly.

<img src="https://raw.githubusercontent.com/ligenxxxx/hdzero-vtx-docs/main/site/img/stick_command.png" style="width:100">

## Menu

### VTX Menu

### Camera Menu

### FC Menu

## Smartaudio Protocol
