# VTX Targets

## Summy

|           VTX Name           |    Whoop(EOL)    |        Whoop Lite        |    Race V1(EOL)    |    Race V2(EOL)    |       Race V3       |              Freestyle V1 (EOL)              |                  Freestyle V2                  |
| :--------------------------: | :---------------: | :----------------------: | :-----------------: | :-----------------: | :-----------------: | :--------------------------------------------: | :--------------------------------------------: |
| **Dimension(mm x mm)** |       32x32       |          32x32          |        27x45        |        34x34        |        28x32        |                     40x40                     |                     29x30                     |
|  **Mounting Pattern**  | 25.5x25.5<br />M2 | 25.5x25.5<br />M2 (Soft) | 20x20<br />M4(Soft) | 20x20<br />M4(Soft) | 20x20<br />M4(Soft) |              30x30<br />M3(Soft)              |                 20x20<br />M2                 |
|   **Weight(grams)**   |        5.3        |           4.5           |          7          |          6          |         5.5         |                       28                       |                      22.3                      |
|    **Power Input**    |      7V-17V      |          1S-3S          |       7V-17V       |       7V-17V       |       4V-12V       |           2S-6S (2rd batch or later)           |                     7-25V                     |
| **Power Consumption** |       5~6W       |           5~6W           |        5~6W        |        5~6W        |        5~6W        |                     6~15W                     |                     6~15W                     |
|  **RF Power Output**  |    25mW,200mW    |        25mW,200mW        |     25mW,200mW     |     25mW,200mW     |     25mW,200mW     | 25mW,200mW (500mW,<br />1W if with HAM license | 25mW,200mW (500mW,<br />1W if with HAM license |
|    **Secured U.FL**    |        No        |           Yes           |         Yes         |         Yes         |         Yes         |                      Yes                      |                      Yes                      |
|  **Antenna Included**  |   Not included   |       Not included       |    Not included    |    Not included    |    Not included    |                Polarized(RHCP)                |                Polarized(RHCP)                |
|  **Tramp/SmartAudio**  |        No        |        SmartAudio        |     SmartAudio     |     SmartAudio     |        Tramp        |                   SmartAudio                   |                   SmartAudio                   |
|       **Keypad**       |        Yes        |            No            |         Yes         |         Yes         |         No         |                      Yes                      |                      Yes                      |
|    **Application**    |       Whoop       |        TinyWhoop        |        Race        |        Race        |        Race        |                   Freestyle                   |                   Freestyle                   |

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

### HDZero Whoop video Transmitter (EOL)

The HDZero Whoop VTX is a digital HD 720p 60fps video transmitter capable of delivering up to 200mw on 5.8GHz.

The power input range is 7V – 17V (2S – 4S).

**Due to the small clearance of mounting holes, make sure the mounting nuts or gummies will not overlap into
the small components around the holes.**

This VTX is designed for low-speed whoop application. Compared to the other HDZero VTXes, it is more vulnerable to be damaged by crash due to: (1) the UFL connector is easily peeled off due to no antenna retention, and (2) it is not easy for soft mounting. Though the VTX can be mounted on a racing and other high-speed quad, it is highly recommended to consider HDZero Race (V1 or V2) for such application.

This VTX does not support Smart Audio or Tramp.

<img src="https://raw.githubusercontent.com/ligenxxxx/hdzero-vtx-docs/main/site/img/HDZero_Whoop_intro.png" style="width:100">

**Notes:**

- Read first: **General Consideration for VTX installation**
- Soft mount
- Pay extra attention not to damage the small components when trying to remove the serrate corner

### HDZero Whoop List Video Transmitter

The HDZero Whoop lite VTX is a digital HD 720p 60fps video transmitter capable of delivering up to 200mw on 5.8GHz.

The power input range is 2.8V – 13V (1S-3S).

- **This VTX does not have reserve polarity protection circuit, it will be permanently damaged if voltage input is reservedly connected. This is number one failure cause.**
- When it is powered by a 5V pad of FC/BEC, make sure that 5V has 1.5A current output.
- When it is powered by an 1S battery directly, note that a rapid throttle up may cause voltage drop below to 2.8V instantly, and that will cause video drop.
- There is no need for an external capacitor when it connects with FC/BEC or 1S battery. However, it is strongly suggested to put on capacitor when powered by a 3S battery.

This VTX has protection cases mounted on both sides. These metal cases are grounded, and to provide protection from crash. They can be removed for tiny whoop quad which cares about every added gram.

This VTX includes M3/M2 gummies for soft mounting, and zip ties for antenna retention. Though the VTX can be mounted on a racing and other high-speed quad, it is highly recommended to consider HDZero Race (V1 or V2) for such application.

<img src="https://raw.githubusercontent.com/ligenxxxx/hdzero-vtx-docs/main/site/img/HDZero_WhoopLite_intro.png" style="width:100">

| No. | Function                  |
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

### Race V1

...

### Race V2

...

### Race V3

...

### Freestyle V1

...

### Freestyle V2

...
