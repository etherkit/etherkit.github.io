---
title: OpenBeacon Troubleshooting
keywords: openbeacon, troubleshooting
summary: "OpenBeacon Troubleshooting Tips"
sidebar: openbeacon_sidebar
permalink: openbeacon_troubleshooting
folder: openbeacon
---

## DC Voltages

Here is a list of typical DC voltages at the 3 transistors in the transmitter when operated off of +13.7 VDC. Since Q1 and Q2 voltage come from a regulator, your measurements should be similar (within about 10%). If you are using a power supply voltage other than +13.7 VDC, your measurements for Q3 will vary. Try to provide +13.7 VDC for checking or scale your results as appropriate.

### Q1

Collector: 4.5 V
Base: 2.2 V
Emitter: 1.7 V

### Q2

Collector: 4.2 V
Base: 1.5 V
Emitter: 0.8 V

### Q3

Collector: 12.9 V
Base: 2.0 V
Emitter: 1.4 V

## AC Waveforms

Note that these measurements were taken on the 30 Meters band version, but the amplitudes should be similar for each band.

{% include image.html file="OpenBeaconQ1Emitter.png" alt="Q1 Emitter" caption="Q1 Emitter" %}

{% include image.html file="OpenBeaconQ2Base.png" alt="Q2 Base" caption="Q2 Base" %}

{% include image.html file="OpenBeaconQ2Emitter.png" alt="Q2 Emitter" caption="Q2 Emitter" %}

{% include image.html file="OpenBeaconC19.png" alt="C19" caption="C19" %}

{% include image.html file="OpenBeaconOutput.png" alt="Output (across 50 ohm load)" caption="Output (across 50 ohm load)" %}

{% include links.html %}
