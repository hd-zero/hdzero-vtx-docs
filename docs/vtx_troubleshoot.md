# Troubleshoot

## No RF output

### Description

- VRX/Goggle cannot scan the VTX signal

### Solutions

#### 1. Re-update firmware

- Update to the latest version.
- Make sure the firmware types matches your VTX.

#### 2. Check the red and blue LED status

##### 1). The red LED is off or unstable

The red LED is directly driven by the system's 5V power supply. If the red LED is not lit and stable, it is usually because there is a problem with the power supply.

- Make sure the voltage and maximum current of the power supply are within the specifications.
- Check if any components are cracked.
- There may be a fault with your VTX's power supply system, you can use a multimeter to measure the voltage test pad to verify it if you have the hardware knowledge.

##### 2). The blue LED never lights up

When the 5680 is initializing, in normal operation, it will first configure the blue LED to be on to indicate that the 5680 mcu has started.  If it does not, check the following:

- If you plug in the Quad battery while the FC is connected to the PC, the VTX may fail to boot although this does not happen often.
- There may be a fault with your VTX's power supply system, you can use a multimeter to measure the voltage test points to verify it if you have the hardware knowledge.

##### 3). The blue LED stays on

Check the following:

- Replace other camera or MIPI cable.
- Check whether the pins of the MIPI socket are clean and intact and ensure that the MIPI cable is properly clipped into place.
- Check whether the pins of the 5680 chip are clean.
- Use the colorbar firmware to test to make sure the RF part works properly.

##### 4). The blue LED flashes 2 short (1/4s) pulses every four seconds (Camera not detected)

At the end of VTX initialization, if the camera is not detected, the blue LED will flash the pattern described.
(The foxeer digisight v3 camera may not show as detected but this does not affect the VTX output RF.)

Check the following:

- Replace other camera or MIPI cable.
- Check whether the pins of the MIPI socket are clean and intact and ensure that the MIPI cable is properly clipped into place.
- Check whether the pins of the 5680 chip are clean.

##### 5). The blue LED flashes 3 short (1/4s) pulses every four seconds (Overheat protection)

The VTX does not normally overheat when moving through air.
If using the VTX on a bench always use a fan too aid cooling, otherwise try switching to a lower power mode.

Note : For HDZ Freestyle V1/V2, if the VTX overheats, the RF will be automatically shut down until the Quad is armed or repowered.

##### 6). The blue LED flashes 4 short (1/4s) pulses every four seconds (RF chip failure)

Your VTX's RF chip dm6300 is damaged, at least it no longer responds to dm5680.

##### 7). The blue LED flashes 1 long (1s) and 1 short (1/4s) pulses every four seconds (0mW mode)

Your VTX may be in 0mw mode. You can exit using the following method:

- Quad + VTX power on
- Connect Quad to Betaflight configurator
- Enter VTX page, set power from 0mw to others

##### 8). The blue LED flashes 1 long (1s) and 2 short (1/4s) pulses every four seconds (Pit mode)

Your VTX may be in Pit mode. You can exit using the following method:

- Quad + VTX power on
- Connect Quad to Betaflight configurator
- Enter VTX page, set Pitmode to Off

## Received video exception

### Desciption

- There is noise at the edge of the object.
- Color is wrong.

### Solutions

#### 1. Re-update firmware

- Update to the latest version.
- Make sure the firmware types matches your VTX.

#### 2. Enter the camera menu, reset and save

#### 3. Check VTX PCB

- Check whether the pins of the mipi socket are intact and ensure that the mipi cable is fastened.
- Check whether the pins of the 5680 chip are clean.

#### 4. Cross testing

Replace the VTX, camera, and  cables respectively to identify where the problem lies.

#### 5. Check power supply

An unclean power supply may cause the camera to have the wrong color.

Please use a DC stabilized voltage source for testing or use a battery for direct power supply.

## OSD is not display

### Description

### Solutions

#### 1. Re-update firmware

- Update to the latest version.
- Make sure the firmware types matches your VTX.

#### 2. Check hardware connections

- **VTX TX** connects to **FC RX**
- **VTX RX** connects to **FC TX**
- Do not connect VTX to the FC's soft serial port.
- Try other FC UART ports.

#### 3. Check FC configuration

##### 1). Set the function of the FC serial port occupied by VTX, save and restart.

- For Betaflight, you need to set uart peripheral to **VTX(MSP+DISPLAYPORT).** The picture below shows setting UART3 to OSD.

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/Betaflight_port_config.png" style="width:100">

- For iNav, you need to set uart Peripheral to **MSP DisplayPort**. The picture below shows setting UART5 to OSD.

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/iNav_port_config.png" style="width:100">

##### 2). Unsupported OSD items

There are some OSD items that require hardware support to actually be enabled, which depends on FC rather than VTX. For example, OSD items related to GPS can only be displayed when FC actually detects the GPS module.

## OSD display unstable

### Description

- OSD flashing
- OSD VTX channel/pwr display **?:?:?**
- OSD refresh slowly
- Wrong OSD location

### Solutions

#### 1. Re-update firmware

- Update to the latest version.
- Make sure the firmware types matches your VTX.

#### 2. Reduce OSD items

If too many OSD items are turned on, the carrying capacity of the uart may be exceeded, which may cause individual OSD items to be unable to be displayed.

#### 3. Close SmartAudio

It is normal for the OSD to flash when SmartAudio is configuring VTX. Please turn off SmartAudio if you don't need it.

## Snowflakes at close range

### Description

### Solutions

#### 1. Re-update firmware

- Update to the latest version.
- Make sure the firmware types matches your VTX.

#### 2. Check VTX configuration

Make sure pit mode is off

#### 3. Avoid RF interference

* There may be interference sources in the current channel. Switch to other channels.
* The RF power of the remote control tuner is too high. Make sure the turner is at least 20cm away from Goggle or VRX.
* When VTX and VRX or Goggle are too close (less than 1 meter), it is normal for a small amount of snowflakes to appear.

#### 4. Build Quad Correctly

* Check whether the VTX antenna is installed securely. Try to make sure that the antenna is not blocked by the carbon fiber of the quad or the battery.
* Replace other antenna for VTX.
* The top of VTX should be at least 1cm away from the carbon fiber.
* Add filter capacitors to your Quad.

#### 5. Check VTX hardware

- Check the front and back of the VTX to see if any components are cracked or falling off.
- Check whether the PA is damaged.
  - For Freestyle V1 VTX, when the power is off, measure whether the two test points named 5V0 on the front are short-circuited to ground. If short-circuited, it means the PA is damaged.
    ![img](https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_FreestyleV1_PD.png)
  - For Freestyle V2 VTX, If after powering on, the red light in the position shown below lights up, it indicates that the PA has been damaged.![img](https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_FreestyleV1_PD.png)
  - For other VTXes. Measure the voltage from test point PD to GND in the power-on state. Generally, when PD is less than 0.2V, the PA is considered to be working abnormally.
    - HDZero Whoop VTX
      ![img](https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_Whoop_PD.png)
    - HDZero WhoopLite VTX
      ![img](https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_WhoopLite_PD.png)
    - HDZero Race V1 VTX
      ![img](https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_RaceV1_PD.png)
    - HDZero Race V2 VTX
      ![img](https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_RaceV2_PD.png)
    - HDAZero Race V3 VTX
      ![img](https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_RaceV3_PD.png)

## VTX cannot update firmware

### Description

- PC/Goggle/VRX cannot detect VTX.
- VRX does not start updating VRX.
- Foxeer VTX cannot be updated by HDZero Programmer or Goggle

### Solutions

#### 1. Make sure the SD card is formatted as FAT32.

#### 2. Make sure the PIN pin of the upgrade socket is intact.

- Bad socket
  ![img](https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/bad_upgrade_socket.jpg)
- good socket
  ![img](https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/good_upgrade_socket.jpg)

#### 3. Updated HDZero Programmer to support Foxeer VTX.

#### 4. Goggle does not currently support updating Foxeer VTX.

#### 5. If you have a keypad plugged in, remove it.

## VTX interferes with GPS

### Description

After turning on VTX RF, the GPS will lose 4~5 satellites.

### Solutions

#### 1. The VTX installation location is far away from the GPS module.

#### 2. Keep the VTX antenna away from the GPS module.

## FC dropping to bootloader

### Description

In versions of Betaflight prior to 4.4.2, when MSP+OSD is enabled on a uart connected to an HDZero VTX and the VTX is unpowered (such as when configuring with only USB power), the FC will be prone to crash to DFU mode when switching pages in Configurator.
A discussion of this problem can be seen [here](https://github.com/betaflight/betaflight/issues/12723)

INav is unaffected.

### Solutions

#### 1. Upgrade to Betaflight 4.4.2 or later

#### 2. A work around for this problem was to add a 200ohm resistor between the wire from FC UART.TX to VTX UART.RX

