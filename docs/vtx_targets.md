# VTX Targets

## Summary

|          VTX            | Weight| Size<BR>(mm)         | Mounting Pattern  | Voltage Input | Power</BR>Consumption | RF Power Output |                         Secured U.FL | Antenna | Tramp/SmartAudio| Keypad | Application |
| ----------------------: | ----: | :---------------: | :---------------: |:-----------: | :----------------: | :-------------: |                         :----------: | :---------------: | :----------:    | :----: | :---------: |
| **Eco**                 | 4.5g  | 32x32             | 25.5x25.5 M2(Soft)|4V-12V        |  5~6W	    | 25mW,200mW                                  | Yes         | Dipole          | No                | Yes    | TinyWhoop |
| **Freestyle V2**        | 22.3g | 29x30             | 20x20 M2          |7-25V         |  6~15W          | 25mW,200mW <br />(500mW,1W ***(a)*** )| Yes         | RHCP            | SmartAudio        | Yes    | Freestyle |
| **Freestyle V1 (EOL)**  | 28.0g | 40x40             | 30x30 M3(Soft)    |2S-6S ***(b)***       |6~15W| 25mW,200mW <br />(500mW,1W ***(a)*** )| Yes         | RHCP            | SmartAudio        | Yes    | Freestyle |
| **Race V3**             | 5.5g  | 28x32             | 20x20 M4(Soft)    |4V-12V        |  5~6W           | 25mW,200mW                                  | Yes         | No              | Tramp             | No     | Race      |
| **Race V2(EOL)**        | 6.0g  | 34x34             | 20x20 M4(Soft)    |7V-17V        |  5~6W           | 25mW,200mW                                  | Yes         | No              | SmartAudio        | Yes    | Race      |
| **Race V1(EOL)**        | 7.0g  | 27x45             | 20x20 M4(Soft)    |7V-17V        |  5~6W           | 25mW,200mW                                  | Yes         | No              | SmartAudio        | Yes    | Race      |
| **Whoop Lite**          | 4.5g  | 32x32             | 25.5x25.5 M2(Soft)|1S-3S         |  5~6W           | 25mW,200mW                                  | Yes         | No              | SmartAudio        | No     | TinyWhoop |
| **Whoop(EOL)**          | 5.3g  | 32x32             | 25.5x25.5 M2      |7V-17V        |  5~6W           | 25mW,200mW                                  | No          | No              | No                | Yes    | Whoop     |

**(a)** Only in permitted regions with HAM Licence<BR>
**(b)** 2nd batch or later


## **General Consideration for VTX installation**

### **Caution: UFL Connectors Are Fragile**

All HDZero VTXes use an U.FL connector for its smaller footprint and lighter weight. However, it is not a mechanically strong connector. Treat it as if it’s made of glass. Here are notes for installing and uninstalling an antenna:

- Never run a cable from the UFL connector straight off the side of a board. Instead, run the antenna cable towards the middle of the board, and secure it in one of the following ways:
  - Hot glue or E6000 glue
    - Avoid using glue on top of the hot components on the board.
    - Preferably, apply glue to the side of the board where the cable leaves the top of the board.
  - Kapton tape to secure it to the surface of the VTX
  - Zip tie it to a nearby standoff
- Unless you need maximum RF performance or minimum weight, consider a UFL->SMA pigtail for larger builds. This allows you to thoroughly secure the SMA connector to your quad to prevent movement of the antenna cable.
- When removing the antenna, go very slowly and pull gently on the antenna so that one side of the UFL slides off first. There are tools designed to remove/insert UFL connectors from their sockets, which can help avoid damage to the UFL connector or socket.

Please visit the following link for more information:

[https://www.facebook.com/groups/hdzero/permalink/448657693828864/](https://www.facebook.com/groups/hdzero/permalink/448657693828864/)

### Powering the VTX: BEC or VBAT

Using a battery eliminator circuit (BEC) is highly recommended to avoid voltage spikes, which can damage the VTX. Although you can power the VTX directly from the battery (VBAT), a BEC will provide more consistent power and will help absorb any voltage spikes, protecting your VTX from over-voltage conditions.

It is important to select a BEC that provides voltage that is within the range of what the VTX accepts, and that is capable of supplying enough current to power the VTX. Whether you are using a BEC that is built into your flight controller or a standalone BEC, be sure to check its voltage and current ratings and compare them to the required voltage and current for your VTX.

All the FCs that include an integrated BEC for DJI VTXes should also work for HDZero VTXes.

To summarize:

- **All HDZero VTXes, except Freestyle Batch 2 VTX or later, do not support 6S VBAT.**
- Check your FC specs to see if you can run your VTX from the FC’s BEC;
- If not, you could run the VTX from a suitable standalone BEC;
- If not, solder a capacitor between the +V and Ground on the VTX. Running on VBAT is always the last choice due to the challenging voltage environment in a quad.

### Mounting Considerations

It is very important to keep some distance between the VTX and ESC/FC boards for the following reasons:

- The RF portion of VTX is vulnerable to electronic noise caused by ESC/motors;
- The RF signal can be bounced back from surfaces of boards or carbon fiber plate, and fed back to the power amplifier in the VTX. This will deteriorate the RF signal integrity and could damage the amplifier.

To avoid these concerns, follow this guidance for mounting the VTX:

- If the VTX is mounted on the top of the stack, please keep 5mm distance from the top carbon fiber plate.
- Avoid mounting the VTX in the middle of the stack.
- If the VTX is mounted on the bottom of the stack, the VTX needs to be upside down (U.FL socket faces down) and needs to have a minimum of 5mm distance from the  bottom carbon fiber plate.

## Targets

### HDZero Eco Video Video Transmitter

HDZero ECO Bundle is designed to bring digital FPV to more pilots by offering a low cost, light weight, and durable alternative to analog video. The digital video signal has stable color reproduction and 720p progressive scan video with the low latency HDZero is known for.
This budget-friendly Air Unit is a groundbreaking product—it's the first VTX/camera combination that utilizes a HD composite video signal, eliminating the need for a delicate MIPI cable.
The ECO FPV System was meticulously designed for ultra-lightweight drones like Tiny Whoops, where every fraction of a gram counts. The camera's huge 98deg vertical FOV is perfect for fast indoor proximity flying. The ECO VTX weighs approximately 4.5g, while the camera (including wires) comes in at about 1.6g. With the included 0.2g dipole antenna, the entire Eco Bundle weighs about mere 6.3g in total.

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_Eco_intro.png" style="width:100">

#### HDZero Eco VTX Specifications

- Composite HD Video Interface
- 1S-3S Input
- 25mW/200mW RF Output
- 25 x 25 M2 Soft Mounting
- Antenna Retention
- 4.5grams/4mm Thickness

#### HDZero Eco camera Specifications

- 14mm wide x 16 tall x 13mm thick
- 1.6g weight with cable
- 1/3” CMOS sensor
- FOV: 4:3  D:150° H:120° V:98°
- Suggested Setting
  - Sharpness: 15
  - Saturation: 8
  - R Surp: 8
  - Brightness: 45



### HDZero Freestyle V2 Video Transmitter

The HDZero Freestyle V2 VTX is our 2nd generation 5.8GHz digital video transmitter which can be fitted into most 3-5-inch HD drones. All sockets are well protected by the CNC case that provides durability, RF shielding and improved signal integrity. A wire harness is included for solderless connection for power and MSP UART port. The antenna and MIPI cable are secured by the included retention bar and screws.

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_FreestyleV2_intro_1.png" style="width:100">

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_FreestyleV2_intro_2.png" style="width:100">

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_FreestyleV2_intro_3.png" style="width:100">

| No. | Description            |
| :-: | ---------------------- |
|  1  | Secured MIPI Connector |
|  2  | M2 Mouting Hole        |
|  3  | Secured u.FL Connector |
|  4  | Keypad Connector       |
|  5  | FW Update Connector    |
|  6  | Power/UART Connector   |
|  7  | Power/UART Harness     |

| Power/UART Connector | Cable Color | Connected with      |
| -------------------- | ----------- | ------------------- |
| Ground               | Black       | Ground              |
| Power                | Red         | Power               |
| RX                   | Yellow      | FC TX               |
| TX                   | White       | FC RX               |
| SA                   | Blue        | FC SA(TX), Optional |



### HDZero Freestyle V1 Video Transmitter(EOL)

The HDZero Freestyle V1 VTX offers unprecedented range and performance for the HDZero 5.8GHz digital FPV system. With its high maximum output power and robust construction, this VTX is perfect for freestyle and long-range builds.

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_FreestyleV1_intro_1.png" style="width:100">

With a tested maximum range of more than 18 miles, the Freestyle V1 VTX will transmit a digital FPV feed as far as you're willing to fly. Not interested in long range? You'll also see better performance in urban environments and around obstacles, with none of the color noise or multipath interference issues of analog video.

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_FreestyleV1_intro_2.png" style="width:100">

| No. | Description            |
| :-: | ---------------------- |
|  1  | Secured MIPI Connector |
|  2  | Keypad Connector       |
|  3  | M3 Mouting Hole        |
|  4  | Secured u.FL Connector |
|  5  | FW Update Connector    |
|  6  | Power/UART Connector   |
| 7* | BEC Power In (2S-6S)   |
|  8  | BEC Power Out Pad      |
|  9  | RHCP Antenna           |
| 10 | Power/UART Harness     |

***: BEC is included for first Batch only.**

| Power/UART Connector | Cable Color | Connected with       |
| -------------------- | ----------- | -------------------- |
| Ground               | Black       | Ground               |
| Power                | Red         | Power*               |
| RX                   | Green       | FC TX                |
| TX                   | Yellow      | FC RX                |
| SA                   | Blue        | FX SA (TX), Optional |

***: The 1st batch supports 4S MAX.**

The 1st batch of Freestyle V1 VTX, supports 2S-4S, A BEC supporting 2S-6S is included.

The 2nd batch and later, supports 2S-6S, and the BEC is *not* included.

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_FreestyleV1_intro_3.png" style="width:100">

**Important Notes:**

- **Do not directly power this VTX with a 5S/6S battery for the 1st batch.**
  - **Use 2S-4S VBAT, or included BEC, or FC with built-in BEC**
  - **The Freestyle VTX consumes up to 15W. If it is connected with FC that has a built-in BEC output, make sure the BEC can provide enough current. For example, if the BEC provides 10V, it needs a minimum of 1.5A current output.**
- **Removing the heat sink is not recommended because it is part of the design.**
- **Rotate the antenna as shown above before detaching it to reduce the risk of peeling off the UFL connector.**



### HDZero Race V3 Video Transmitter

Designed for FPV racing, the HDZero Race V3 VTX is our 3rd generation digital video transmitter. With a voltage range starting at 4V, it can be powered by the 5V 1.5A regulator of most FC's or up to 12V for FC's that include a HD VTX plug. It is small (28x32x5mm) and light (5.5 grams). With a width of only 28mm, the VTX is now a similar width to many FC's, which improves durability and reduces weight. The antenna is securely attached with a metal bar and screws. No soldering needed – just plug the wire harness into a compatible HD-ready FC.

The HDZero Race V3 VTX is designed with durability in mind, rather than weight. It is made with a 1.6mm thick PCB, in comparison to the 1.0mm PCB used in the Whoop lite VTX. Moreover, it uses more large package size components for stability consideration. For the smaller components, an additional glue coating is applied to increase crash protection.

The HDZero Race V3 VTX offers high-quality video in 540p90, 720p60 and 1080p30 resolutions with 25/200mW switchable power on 5.8GHz.

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_RaceV3_intro_1.png" style="width:100">

| No. | Description                                                                                                                                                    |
| :-: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|  1  | VTX-R3 board                                                                                                                                                   |
|  2  | SmartAudio/Tramp (Optional)                                                                                                                                    |
|  3  | Wire harness to connect with FC<br />Red = BEC 4-12V<br />Black = GND<br />White = VTX UART TX (Connect to FC RX)<br />Yellow = VTX UART RX (Connect to FC TX) |
|  4  | Rubber Grommet (M4 to M3)                                                                                                                                      |
|  5  | Metal bar and screws for securing antenna                                                                                                                      |

#### Connection

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_RaceV3_intro_2.png" style="width:100">

The right figure shows the typical connection with FC supports MSP VTX protocol.

The Race V3 supports direct connect with Ghost RX via its SA/Tramp port(TBD)



### HDZero Race V2 Video Transmitter (EOL)

The HDZero Race VTX is a digital HD 720p 60fps video transmitter capable of delivering up to 200mw on 5.8GHz. It works with the Shark Byte RX5.1 goggle module to transmit video, and with a remote controller to wirelessly control the parameters for the transmitter and camera.

The power input range is 7V – 17V (2S – 4S).

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_RaceV2_intro_1.png" style="width:100">

| No. | Description                             |
| --- | :-------------------------------------- |
| 1   | Power in (G=Ground, V=7-17V)            |
| 2   | T1/R1 UART Connection to FC             |
| 3   | T2, Reserved, R2/SA, SA Pin             |
| 4   | u.FL Antenna Connector                  |
| 5   | u.FL Antenna Retention Holes            |
| 6   | MIPI Connector                          |
| 7   | MIPI Connector Retention Holes          |
| 8   | Firmware Update Connector               |
| 9   | Power On LED (red)                      |
| 10  | Status LED (blue)                       |
| 11  | u.FL Antenna Retention Screws/Nut/Plate |
| 12  | Rubber Grommet (M4 to M3), 1mm O-Ring   |
| 13  | Zip ties                                |
| 14  | Connecting wire                         |
| 15  | 20x20 M4 mounting hoNoles               |

#### Mounting a u.FL antenna or pigtial

There are 2 methods to mount the antenna on VTX:

- Use included retention screws, nuts and plate;
- Use included zip-ties.

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_RaceV2_intro_2.png" style="width:100">

#### Connecting MIPI cable

Use the included zip-tie to secure MIPI cable and protect MIPI connector.

**Notes:**

- Read first: **General Consideration for VTX installation**
- **Make sure to use a wider top plate to fully c****over this VTX for protection.**



### HDZero Race V1 Video Transmitter (EOL)

The HDZero Race VTX is a digital HD 720p 60fps video transmitter capable of delivering up to 200mw on 5.8GHz.

The power input range is 7V – 17V (2S – 4S).

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_RaceV1_intro_1.png" style="width:100">

| No. | Description                                            |
| :-: | :----------------------------------------------------- |
|  1  | Power/UART Connector                                   |
|  2  | FW Update Connector                                    |
|  3  | MIPI Connector                                         |
|  4  | u.FL Antenna Connector                                 |
|  5  | u.FL Antenna Retention Holes                           |
|  6  | Power on LED(red)                                      |
|  7  | Status LED(blue)                                       |
|  8  | Mounting Holes (20x20 M4)                              |
|  9  | Zip Ties (4x)                                          |
| 10 | u.FL Antenna Retention<br />Scews(4x)/Nut(4x)/Plate    |
| 11 | Rubber Grommet(M4 to M3 4x)                            |
| 12 | Power/UART harness (20cm) and a PH2.0 connector (6P) |

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_RaceV1_intro_2.png" style="width:100">

| Power/UART Connector | Cable Color | Connected with |
| :------------------- | ----------- | -------------- |
| Ground               | Black       | Ground         |
| Power                | Red         | Power          |
| T1                   | Green       | FC.RX          |
| R1                   | Yellow      | FC.TX          |
| T2                   | White       | DO NOT CONNECT |
| R2/SA, Optional     | Gray        | FC.SA(TX)      |

#### Connection between Race V1 VTX and FC

There are 3 methods to connect the VTX and flight controller:

- Plug the included harness, cut the cables to appropriate length, and solder them on FC
- Use solder pads on the back of the connector
- For FCs having BEC and UART connector, install harness to the included PH2.0 connector (Shown above), and connect the harness with FC without any soldering.

**Warning: Check that pinout matches the FC pinout before installing to be safe if plugging directly.**

#### Mounting an u.FL antenna or pigtail

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_RaceV1_intro_3.png" style="width:100">

There are 2 methods to mount antenna on VTX:

- Use included retention screws, nuts and plate.
- Use included zip-ties.



### HDZero Whoop Lite Video Transmitter

The HDZero Whoop lite VTX is a digital HD 720p 60fps video transmitter capable of delivering up to 200mw on 5.8GHz.

The power input range is 2.8V – 13V (1S-3S).

- **This VTX does not have reserve polarity protection circuit, it will be permanently damaged if voltage input is reservedly connected. This is number one failure cause.**
- When it is powered by a 5V pad of FC/BEC, make sure that 5V has 1.5A current output.
- When it is powered by an 1S battery directly, note that a rapid throttle up may cause voltage drop below to 2.8V instantly, and that will cause video drop.
- There is no need for an external capacitor when it connects with FC/BEC or 1S battery. However, it is strongly suggested to put on capacitor when powered by a 3S battery.

This VTX has protection cases mounted on both sides. These metal cases are grounded, and to provide protection from crash. They can be removed for tiny whoop quad which cares about every added gram.

This VTX includes M3/M2 gummies for soft mounting, and zip ties for antenna retention. Though the VTX can be mounted on a racing and other high-speed quad, it is highly recommended to consider HDZero Race (V1 or V2) for such application.

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_WhoopLite_intro.png" style="width:100">

| No. | Description               |
| :-: | :------------------------ |
|  1  | MIPI Connector            |
|  2  | Status LEDs               |
|  3  | Power/UART/SA solder pads |
|  4  | u.FL Connector            |
|  5  | Protection Case           |
|  6  | Protection case clipper   |

Solder pad:

| Pad | Function            |
| :-: | :------------------ |
|  G  | Ground              |
|  V  | 2.8V-13V            |
| RX | FC.TX               |
| TX | FC.RX               |
| SA | FC.SA(TX), Optional |

**Notes:**

- Read first: **General Consideration for VTX installation**
- This VTX does not support using keypad to tune channel and RF output power level. Ir is designed to work with flight controller.



### HDZero Whoop video Transmitter (EOL)

The HDZero Whoop VTX is a digital HD 720p 60fps video transmitter capable of delivering up to 200mw on 5.8GHz.

The power input range is 7V – 17V (2S – 4S).

**Due to the small clearance of mounting holes, make sure the mounting nuts or gummies will not overlap into
the small components around the holes.**

This VTX is designed for low-speed whoop application. Compared to the other HDZero VTXes, it is more vulnerable to be damaged by crash due to: (1) the UFL connector is easily peeled off due to no antenna retention, and (2) it is not easy for soft mounting. Though the VTX can be mounted on a racing and other high-speed quad, it is highly recommended to consider HDZero Race (V1 or V2) for such application.

This VTX does not support SmartAudio or Tramp.

<img src="https://raw.githubusercontent.com/hd-zero/hdzero-vtx-docs/main/img/HDZero_Whoop_intro.png" style="width:100">

**Notes:**

- Read first: **General Consideration for VTX installation**
- Soft mount
- Pay extra attention not to damage the small components when trying to remove the serrate corner



## VTX Sockets

|          VTX            | f/w Update Socket | Keypad Socket | Power/UART Socket | HD VTX Plug | Camera Connector |
| ----------------------: | :---------------: | :-----------: | :---------------: | :---------: | :--------------: |
| **Eco**             |         B         |       C       |                  |            |                  |
| **Freestyle V2**        |         B         |       C       |         E         |            |        G        |
| **Freestyle V1 (EOL)**  |         A         |       C       |         E         |            |        G        |
| **Race V3**             |         B         |              |                  |      F      |        G        |
| **Race V2(EOL)**        |         A         |       C       |                  |            |        G        |
| **Race V1(EOL)**        |         A         |       C       |         D         |            |        G        |
| **Whoop Lite**          |         B         |               |                  |            |        G        |
| **Whoop(EOL)**          |         A         |       C       |                  |            |        G        |
| **Foxeer VTX**          |         A         |       C       |                  |            |        G        |



| f/w Update Socket  
|:-------------------
| **A:** 7-way SH 1.0mm  
| **B:** 7-way SUR 0.8mm 

| Keypad Socket    |
|:-----------------|
|**C:** 6-way SUR 0.8mm|

| Power/UART Socket |
|:------------------|
| **D:** 6-way GH 1.25mm|
| **E:** 5-way GH 1.25mm|

|   HD VTX Plug    |
|:-----------------|
|**F:** 6-way GH 1.25mm|

|      Camera Connector        |                  
|:-----------------------------|
| **G:**  20 Pin 0.4mm Pitch (MIPI)|
                            

|Miscellaneous|
|:---------------------------------|
|Keypad PCB Socket: 6-way GH 1.25mm|

