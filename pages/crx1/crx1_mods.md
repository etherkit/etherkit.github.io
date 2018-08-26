---
title: CRX1 Modifications
keywords: crx1, mods, modifications
summary: "Modifications you can make to your CRX1."
sidebar: crx1_sidebar
permalink: crx1_mods
folder: crx1
---

## External VFO

You can get a wider range of tuning by using an external VFO with the CRX1. A handy port (J2) is provided to easily interface your external VFO with the CRX1. Simply disconnect power from the VXO before using an external VFO by disconnecting JP1.

### External VFO Requirements

The BF998 dual-gate MOSFET mixer is a voltage driven device, so it has very light power and current requirements, but does need a drive level of 4 to 6 volts peak-to-peak for optimum conversion gain. Since many VFOs and DDS devices are designed to drive a diode-ring mixer at a level of +7 dBm into a 50 ohm load (only about 1.4 Vpp), you may need to modify one of these devices in order to interface them with the CRX1. The best way to do this is to use an amplifier. One stage of voltage amplification should be sufficient. Since the power requirements are so low, no buffer should be needed. It may also be possible to to use a simple step-up transformer to get the VFO voltage level up to 5 Vpp, although that has not yet been tried here at Etherkit.

{% include links.html %}
