## Wireless terminal board

This design is based on a setup by Ryan Roth, mentioned in this [Google Groups thread](https://groups.google.com/g/pal6502/c/w8N0uSgJXQY), and the ESP8266 needs to be [programmed with his firmware](https://github.com/ryaneroth/ESP8266-SerialTelnet). For convenience, I keep a [copy of his repo here](https://github.com/eduardocasino/ESP8266-SerialTelnet).

![WiFi auxiliary board](https://github.com/eduardocasino/kim-1-mtu-motherboard/blob/main/kim-1-aux-card-esp/images/kim-1-aux-card-esp.png?raw=true)

## Firmware install instructions

1. Download and install the latest **Arduino IDE 2.X (preferred) or 1.6.X** from [https://www.arduino.cc/en/Main/Software](https://www.arduino.cc/en/Main/Software)

2. Install **ESP8266** Arduino support using Boards Manager: [https://github.com/esp8266/Arduino#installing-with-boards-manager](https://github.com/esp8266/Arduino#installing-with-boards-manager)

    ***Only*** for IDE 1.6.X, force install version >= 2.4.0. Replace package URL with: [https://github.com/esp8266/Arduino/releases/download/2.4.0-rc1/package_esp8266com_index.json](https://github.com/esp8266/Arduino/releases/download/2.4.0-rc1/package_esp8266com_index.json)

3. Install Install the following libraries:
    * WifiManager: [https://github.com/tzapu/WiFiManager#install-through-library-manager](https://github.com/tzapu/WiFiManager#install-through-library-manager)

4. Put the three bridges in the "**FLASH**" position and connect the board to your computer using an USB to serial adapter.

5. Select board `Generic ESP8266Module`

6. Upload the Sketch contained in `telnetserver` folder from the [ESP8266-SerialTelnet](https://github.com/eduardocasino/ESP8266-SerialTelnet) repo.

7. The moment the `Connecting...` message appears in the console, press the "**RESET**" button and, while holding it", press momentarily the "**FLASH**" button. Then, release the "**RESET**" button. Wait until the sketch is uploaded.

8. Connect to the ESP8266 WiFi network and go to "http://192.168.4.1". Configure connection to your AP, set password, then switch back to your local wifi

9. Disconnect the card and put the bridges back to the "**RUN**" position. Now, you can install it into the motherboard.

10. Connect to the ESP8266 using a Telnet client. Set local echo to off.
