---
title: CRX1 Transmitter Integration
keywords: crx1, transmitter
summary: "How to integrate the CRX1 with a transmitter"
sidebar: crx1_sidebar
permalink: crx1_tx
folder: crx1
---

_Please do not use a transmitter with an output power greater than 5 watts with the CRX1 unless you provide an alternate means of T/R switching._

The CRX1 is designed to easily integrate with a companion 40 meter QRP CW transmitter. It includes a T/R switch (really just a filter to drop the transmitted signal to a low enough level to not damage the CRX1 front end), muting, and an optional sidetone (use jumper JP2 to enable or disable the sidetone). Your transmitter will need to use grounded keying in order to be compatible with the CRX1. You will need the following accessories in order to integrate the CRX1 with a transmitter:

* 1 - 1/8" stereo "Y" adapter (one 1/8" stereo plug to two 1/8" stereo jacks)
* 1 - 1/8" male-to-male stereo jumper cables
* 1 - 50-ohm BNC "T" adapter (one BNC male to two BNC female)
* 1 - 50-ohm BNC coax cable jumper

First, plug the 1/8" stereo "Y" adapter into the CRX1 "Key Line" port, use one of the 1/8" male-to-male stereo jumper cables to connect one port of the "Y" adapter to the key line of the transmitter, then connect your key or keyer to the other port of the "Y" adapter. Next, connect the male side of the BNC "T" adpater to the CRX1 antenna port, use a coax jumper to connect one port of the BNC "T" to the transmitter antenna port, then connect the actual antenna cable to the other BNC "T" port.

In this configuration, the CRX1 will automatically mute and send sidetone (if enabled) whenever the transmitter is keyed, without the need to use a manual T/R switch.

{% include links.html %}
