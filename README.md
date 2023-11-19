# KIM-1 Motherboard for MTU Cards

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

**WARNING**: This board has not been tested yet, use at your own risk!

## Licensing

This is a personal project that I am sharing in case it is of interest to any retrocomputing enthusiast and all the information in this repository is provided "as is", without warranty of any kind. I am not liable for any damages that may occur, whether it be to individuals, objects, KIM-1 computers, kittens or any other pets.

[![license](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc/4.0/)

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

See the LICENSE.md file for details.

## Acknowledgements

* Hans Otten and his [Retro Computing blog](http://retro.hansotten.nl/). Documentation of MTU's line of hardware expansions for the KIM-1
