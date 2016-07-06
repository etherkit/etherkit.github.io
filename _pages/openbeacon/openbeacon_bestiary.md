---
title: OpenBeacon Signal Bestiary
keywords: openbeacon, signal, identification, bestiary
summary: "Help with signal identification"
sidebar: openbeacon_sidebar
permalink: openbeacon_bestiary
folder: openbeacon
---

## QRSS

QRSS is the original, classic slow-speed mode. Regular CW is sent a very slow speed (typically 3-12 seconds per dit).

{% include image.html file="QRSSExample.png" alt="QRSS Example" caption="QRSS Example" %}

## DFCW

In DFCW, the carrier is constantly on and the frequency of the carrier is shifted up a few Hertz to indicate Morse Code elements.

{% include image.html file="DFCWExample.png" alt="DFCW Example" caption="DFCW Example" %}

## Sequential Multi-Tone Hellschreiber

Sequential Multi-Tone Hellschreiber (abbreviated S/MT Hell) "paints" characters on the receiving station's waterfall display. In OpenBeacon, this is done by sweeping the tuning of the oscillator from high to low, and turning on the transmitter every time a "pixel" needs to be displayed.

{% include image.html file="HellExample.png" alt="S/MT Hell Example" caption="S/MT Hell Example" %}

## Glyphcode

Glyphcode (a name which I have given as I have not seen a consensus name for this type of transmission) is an offshoot of S/MT Hell. Instead of painting characters, two different symbols are transmitted: one for a Morse Code dah and one for a Morse Code dit. The characters can be customized to your liking. The default glyphs are a visual representation of a dit and dah, although you will often see oppositely-pointing triangles used on the bands.

{% include image.html file="GlyphCodeExample.png" alt="Glyphcode Example" caption="Glyphcode Example" %}

{% include links.html %}
