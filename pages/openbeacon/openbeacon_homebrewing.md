---
title: Homebrewing OpenBeacon
keywords: openbeacon, homebrew
summary: "OpenBeacon Homebrewing Instructions"
sidebar: openbeacon_sidebar
permalink: openbeacon_homebrewing
folder: openbeacon
---

If you are going to roll-your-own OpenBeacon from scratch, it's relatively straightforward to do, but please keep in mind the following things.


## Burning the Firmware
If you are homebrewing OpenBeacon and are burning a copy of the firmware .hex file on your own ATtiny85, then be sure to use the following fuse settings in order for the microcontroller to work correctly:

Low: 0xE1<br/>
High: 0x5D<br/>
Ext: 0xFF

If you are using a \*nix machine, I've included a handy script to burn the firmware and set the fuses called burn_firmware.sh in the firmware/Release folder in the project [GitHub repository](https://github.com/etherkit/OpenBeacon).


{% include links.html %}
