---
title: OpenBeacon Hardware Usage Guide
keywords: openbeacon, hardware
summary: "How to use the OpenBeacon hardware"
sidebar: openbeacon_sidebar
permalink: openbeacon_hw_usage
folder: openbeacon
---

## Powering the OpenBeacon

OpenBeacon is designed to be dual-powered from either a USB port (through J2) or from a +12 VDC power supply (through J1). You may even leave J1 and J2 connected at the same time, as there is diode protection so that only the highest voltage supply is used. While J1 is specified for a nominal voltage of +12 VDC, you may provide between +5 VDC to +14 VDC to OpenBeacon through this jack.

## Controls and Indicators

S1 is used to restart the transmission of the current message buffer at any time.

D2 indicates the current FSK tuning voltage being output to tune the oscillator, while D7 indicates when the oscillator is transmitting.

D1 will never light, as it is reversed-biased and being used as a voltage-variable tuning capacitor, not an indicator.

R20 controls the transmitter output power.

## Calibration

To calibrate the OpenBeacon, you will need:

Stable receiver for the band of your OpenBeacon frequency
QRSS reception program, such as Argo (can be run under WINE in Linux), which can be run on a PC with a sound card connection to the receiver
Non-metallic tweaker screwdriver
50 ohm dummy load
Connect the dummy load to J4 and connect the OpenBeacon to your PC via J2. Issue the command to place the OpenBeacon into calibration mode:

Linux/OS X:

```$ ./openbeacon mode cal```

Windows:

```C:\> openbeacon mode cal```

This sets the OpenBeacon to constantly sweep the FSK output from minimum to maximum. Find the signal on your QRSS program and observe the width of the signal (you will probably want to switch in an attenuator if your receiver has one or set the QRSS program's gain to low). In order to not take over too much of the small QRSS sub-band (usually only 200 Hz wide), we need to set the maximum deviation to approximately 10 Hz. Adjust C3 with the tweaker until the signal is about 10 Hz wide as measured on the QRSS software.

Next, we need to set the carrier within the QRSS sub-band. On 30 meters, this is at 10.140 MHz +/- about 100 Hz. Set your receiver in USB mode at 1 kHz below the 10.140 MHz center frequency. Adjust C5 so that your signal is somewhere within the range of 950 to 1050 Hz on the QRSS software (your choice of where you want to operate the beacon). There is a bit of interactivity between C3 and C5, so double-check your maximum deviation and adjust as needed. You may need to repeat these steps a few times to get them exactly where you want them.

## Some Notes

Frequency stability is of the utmost importance when running a QRSS beacon. In normal CW operation, a drift of 30 Hz would be acceptable, but that is far too much for QRSS. The OpenBeacon is stable with crystal control, but in order to ensure maximum frequency stability and to dampen the effects of any environmental changes, it is best to place the OpenBeacon in a thermal chamber. A small box cut from anti-static foam makes a good chamber. Enclosing this chamber in a second chamber, such as a small styrofoam cooler, would make an excellent permanent system.

There is a good chance that the oscillation frequency will shift a bit when OpenBeacon is connected to an antenna instead of a 50 ohm dummy load. Be sure to re-check your frequency when connected to an antenna for the first time.

R20 controls the OpenBeacon output power. Turn down the power for an extra challenge!

{% include links.html %}
