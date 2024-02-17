# KIM-1 Motherboard for MTU Cards

## **WARNING**

**ALTHOUGH THE CARDS HAVE BEEN TESTED NOW, THERE MAY BE MORE ERRORS. USE AT YOUR OWN RISK!!!**

If you ordered the first revision PCB, please see the "Rev. 1 Fix" section below.

If you ordered earlier revisions of the aux cards (RS-232 and USB), please see the "Aux. Cards Fix" section below. 

## About

Welcome to my KIM-1 Motherboardfor MTU cards repository.

This board follows the MTU standard for the KIM-1 expansion and application buses and enables to connect up to five cards, like the [K-1008](https://github.com/eduardocasino/k-1008-visable-memory-card-replica). All the CPU lines are buffered. Additionally, all signals of the KIM-1 ports are replicated on corresponding edge connectors to allow further expansions.

Two audio jacks allow for cassette deck connection and two optional daughterboards provide IEC and RS-232 or USB serial connections, and also a connector compatible with Corsham's SD Shield.

The MTU bus connects 1 to 1 to the KIM-1 expansion connector with the exception of pins 2,3, 16, 17, 18, 19, 20 and X, because MTU boards use some of these pins for power and expanded 18 bit address bus (See page 33 of the [MTU Fall 1980 6502 Peripherals and Software catalog](hhttp://retro.hansotten.nl/6502-sbc/mtu/) Lines 19 and 20 are connected to pins J (K7) and K (DECODE ENABLE) of the KIM-1 application connector, respectively. Those two signals can be limited to just the first or the first and second connectors by opening some jumpers.

A five screw terminal block provides power connections for both the KIM-1 (GND, +5V and +12V regulated) and the expansion boards (+7.5V and +16V unregulated). 

![components](https://github.com/eduardocasino/kim-1-mtu-motherboard/blob/main/kim-1-mtu-motherboard/images/kim-1-mtu-motherboard.png?raw=true)
![front](https://github.com/eduardocasino/kim-1-mtu-motherboard/blob/main/kim-1-mtu-motherboard/images/kim-1-mtu-motherboard-front.png?raw=true)
![back](https://github.com/eduardocasino/kim-1-mtu-motherboard/blob/main/kim-1-mtu-motherboard/images/kim-1-mtu-motherboard-back.png?raw=true)

Detail of the two auxiliary boards:
![rs232](https://github.com/eduardocasino/kim-1-mtu-motherboard/blob/main/kim-1-aux-card/images/kim-1-aux-card-on-board.png?raw=true)
![usb](https://github.com/eduardocasino/kim-1-mtu-motherboard/blob/main/kim-1-aux-card-usb/images/kim-1-aux-card-usb-on-board.png?raw=true)

This is how an example setup with one K-1008 board and a [RAM/ROM expansion card](https://github.com/eduardocasino/kim-1-mtu-ram-rom) would look like:

![setup](https://github.com/eduardocasino/kim-1-mtu-motherboard/blob/main/kim-1-mtu-motherboard/images/kim-1-with-k-1008-ram-rom.png?raw=true)

**NOTE**: [This expansion board is a much simpler option](https://github.com/eduardocasino/kim-1-mtu-expansion-card) if you just need to connect some MTU cards. Those are engineered so they put less than 1 TTL load on the CPU buses, so no buffering is really needed. Why the buffering, then? Well, just for fun.

## Licensing

This is a personal project that I am sharing in case it is of interest to any retrocomputing enthusiast and all the information in this repository is provided "as is", without warranty of any kind. I am not liable for any damages that may occur, whether it be to individuals, objects, KIM-1 computers, kittens or any other pets.

[![license](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc/4.0/)

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

See the LICENSE.md file for details.

## Rev. 1 Fix

If you tried to build revision 1 of this board, you found out that it does not work (See [Issue #2](https://github.com/eduardocasino/kim-1-mtu-motherboard/issues/2))

You can [install this simple PCB](https://github.com/eduardocasino/kim-1-mtu-motherboard/rev-1-fix) or, alternatively, perform this bodge on the back of the PCB:

Using a cutter, carefully cut these two spokes at pin 19 of U4:

![step1](https://raw.githubusercontent.com/eduardocasino/kim-1-mtu-motherboard/main/rev-1-fix/images/rev-1-fix-cut.png)

Grab a 14 pin IC socket with flat pins. Bend pins 1,2,3,7 and 14 outwards and cut the rest.

Solder wires to the pins as per this image:

![step1](https://raw.githubusercontent.com/eduardocasino/kim-1-mtu-motherboard/main/rev-1-fix/images/ic-solder.png)

Cover the back of the socket with non conductive tape. Attach the wires to these spots on the motherboard:

![step2](https://raw.githubusercontent.com/eduardocasino/kim-1-mtu-motherboard/main/rev-1-fix/images/rev-1-fix-solder.png)

Place a 74LS00 in the socket (check the orientation!) and fix evrything to the PCB using some tape, like in this image. I took K7 from another pin, but it is all the same:

![step2](https://raw.githubusercontent.com/eduardocasino/kim-1-mtu-motherboard/main/rev-1-fix/images/motherboard-bodge.png)

## Aux. Cards Fix

If you tried to build earlier revisions of the auxiliary boards (both RS-232 and USB), you may have found out that they do not work with Corsham's SD Shield, although they work fine with IEC disks (See [Issue #3](https://github.com/eduardocasino/kim-1-mtu-motherboard/issues/3))

If you need them to work with the SD Shield, you can perform this simple fix. **WARNING: Doing so, the cards will no longer work with IEC disks**

The fix is the same for both cards. Using a cutter, carefully cut these two tracks:

![aux-card-fix](https://github.com/eduardocasino/kim-1-mtu-motherboard/blob/main/kim-1-aux-card/images/kim-1-aux-card-fix.png?raw=true)


## Changelog
#### 17/02/2024
* Release Rev. 3 (fixes the auxiliary cards, the motherboard is unchanged)
* IEC socket footprint also supports Commodore-style sockets
* Add instructions to fix original auxiliary boards so they work with IEC disks.

#### 21/01/2024
* Release Rev. 2
* Add instructions to fix Rev. 1 boards.

#### 03/01/2024
* Minor silkscreen update

#### 02/01/2024
* Disable data bus transceiver when DECEN or K7 are active (low)

## Acknowledgements

* Hans Otten and his [Retro Computing blog](http://retro.hansotten.nl/). Documentation of MTU's line of hardware expansions for the KIM-1
