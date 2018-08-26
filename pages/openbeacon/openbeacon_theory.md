---
title: OpenBeacon Theory of Operation
keywords: openbeacon, theory
summary: "A discussion about how OpenBeacon works"
sidebar: openbeacon_sidebar
permalink: openbeacon_theory
folder: openbeacon
---

_Please refer to the [schematic](https://github.com/etherkit/OpenBeacon/raw/master/documentation/OpenBeacon%20Schematic.pdf) for component references._

OpenBeacon is a simple MOPA (master oscillator, power amplifier) transmitter which is keyed and frequency shifted by U1, the Atmel ATtiny85 microcontroller.

Q1, X1 and its surrounding components form a basic Colpitts crystal oscillator, which is keyed by Q4. Larger-value trim capacitor C5 allows setting the transmit frequency at the desired location, while small-value trim capacitor C3 in series with fixed-value C4 controls the maximum frequency shift. LED D1 does not light up in this application. Instead, it is reversed-biased in order to use it as a varactor (voltage controlled capacitance) for tuning the oscillator.

Q2 and its support components provide buffering for the crystal oscillator. Q3 and its surrounding components is the power amplifier which amplifies the oscillator signal up to approximately 300 mW. A low-pass filter consisting of L3, L4, C20, C22, and C24 ensure that any harmonic content is reduced according to FCC regulations.

The power supply system consists of U2, and Schottky diodes D4, D5, D8, and D9. These ensure that regardless of whether J1, J2, or both are connected, that the ATtiny85 will get ~4.5 VDC and that the highest possible voltage will be available to the power amplifier.

USB is implemented in firmware, and only J2, D3, D5, R10, R11, and R15 are needed on the hardware end to support it.

U1 provides a tuning voltage to D1 in order to generate the different operating modes. A PWM signal is generated on pin 3, which is filtered to DC by R1, R2, R3, C1, and C2. D2 gives a visual indication of the FSK activity.

{% include links.html %}
