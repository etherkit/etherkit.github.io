---
title: EtherProg Description and Specifications
keywords: etherprog, description, specifications, specs
summary: "A look at the specifications of the EtherProg and a description of what exactly it does."
sidebar: etherprog_sidebar
permalink: etherprog_specs
folder: etherprog
---

## What is EtherProg?

EtherProg is a bare-bones Atmel AVR in-system programmer (ISP) based on the open source [vusbtiny](http://www.simpleavr.com/avr/vusbtiny) firmware. The [AVRDUDE] open source utility is used in conjunction with EtherProg to flash firmware (along with other functions) to target microcontrollers. EtherProg will be capable of flashing new firmware to any Etherkit product that includes an AVR microcontroller.

## Specifications

* Operates with Windows, OS X, and Linux
* Only requires a free USB port on your PC (a standard USB A-B cable is required)
* Can provide +5 VDC to target (jumper selection)
* Standard 6-pin Atmel AVR ISP header and cable included

## Supported Devices

Programming the following Atmel microcontrollers via AVRDUDE is supported (as listed in the AVRDUDE documentation):

* AT90S1200
* AT90S2313
* AT90S2333
* AT90S2343
* AT90S4414
* AT90S4433
* AT90S4434
* AT90S8515
* AT90S8535
* AT90CAN128
* AT90CAN32
* AT90CAN64
* ATmega103
* ATmega128
* ATmega1280
* ATmega1281
* ATmega1284P
* ATmega128RFA1
* ATmega16
* ATmega161
* ATmega162
* ATmega163
* ATmega164
* ATmega164P
* ATmega168
* ATmega168P
* ATmega169
* ATmega16U2
* ATmega2560
* ATmega2561
* ATmega32
* ATmega324P
* ATmega325
* ATmega3250
* ATmega328P
* ATmega329
* ATmega3290
* ATmega329P
* ATmega3290P
* ATmega32U2
* ATmega32U4
* ATmega48
* ATmega64
* ATmega640
* ATmega644P
* ATmega644
* ATmega645
* ATmega6450
* ATmega649
* ATmega6490
* ATmega8
* ATmega8515
* ATmega8535
* ATmega88
* ATmega88P
* ATmega8U2
* AT90PWM2
* AT90PWM2B
* AT90PWM3
* AT90PWM3B
* ATtiny10
* ATtiny12
* ATtiny13
* ATtiny15
* ATtiny2313
* ATtiny25
* ATtiny26
* ATtiny261
* ATtiny4
* ATtiny4313
* ATtiny44
* ATtiny45
* ATtiny461
* ATtiny5
* ATtiny84
* ATtiny85
* ATtiny861
* ATtiny88
* ATtiny9
* AT32uca0512
* ATmega1286
* ATmega1287
* ATmega162
* ATmega647
* ATmega647
* ATmega82
* ATxmega128A1
* ATxmega128A1revD
* ATxmega128A3
* ATxmega128A4
* ATxmega16A4
* ATxmega192A1
* ATxmega192A3
* ATxmega256A1
* ATxmega256A3
* ATxmega256A3B
* ATxmega32A4
* ATxmega64A1
* ATxmega64A3
* ATxmega64A4

{% include links.html %}
