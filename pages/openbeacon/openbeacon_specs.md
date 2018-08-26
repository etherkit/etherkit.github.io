---
title: OpenBeacon Description and Specifications
keywords: openbeacon, description, specifications, specs
summary: "A look at the specifications of OpenBeacon and a description of what exactly it does."
sidebar: openbeacon_sidebar
permalink: openbeacon_specs
folder: openbeacon
---

## What is OpenBeacon?

OpenBeacon is an open source crystal-controlled QRPp beacon transmitter which can output a variety of slow-speed modes, including QRSS, DFCW, and Sequential Multi-tone Hellschreiber. It is configured via USB port, so there are no jumpers to set and you can easily adjust all of the operating parameters via command line. Once configuration is complete, OpenBeacon may be removed from the PC and operate stand-alone.

OpenBeacon is considered a MEPT (manned experimental propagation transmitter), which means that you should never leave the control of it unattended.

## Specifications

* Frequency: crystal controlled
* Available bands: 80 meters, 40 meters, 30 meters
* Modes: CW, QRSS, DFCW, Sequential Multi-tone Hellschreiber, Glyphcode, WSPR (experimental)
* Power output (nominal): 30 meters: 300 mW, 10 meters: 100 mW (at +13.7 VDC power supply)
* Spectral purity: greatest harmonic <-45 dBc
* Power supply: +5 VDC to +14 VDC
* Current consumption: 50 mA at +5 VDC, 120 mA at +13.7 VDC
* Control via USB on Windows, OS X, and Linux

## What is QRSS/DFCW?

QRSS is a very slow speed CW operating mode where the length of the characters are significantly lengthened in order to allow weaker signals (QRP) to be able to be received on a special spectrum display with a long integration time of minutes to hours. DFCW is a similar mode, where the carrier is left on, and Morse Code characters are formed by shifting the carrier frequency up a few Hz (FSK). Sequential Multi-tone Hellschreiber (often abbreviated S/MT Hell) uses FSK to "paint" characters on the spectrum display so that they show up as graphical characters. Glyphcode uses the S/MT Hell mode to print two glyphs to represent Morse Code characters, one for a dah and another for a dit.

We have a [visual guide](openbeacon_bestiary) available to show you what these modes look like on a waterfall display.

The KnightsQRSS group has an excellent [primer on QRSS](http://knightsqrss.blogspot.com/2010/01/getting-started-with-qrss.html).

## How do I see my signal?

There are receivers known as "grabbers" which are made public by their owners in order for you to spot your own signal, and others. Most of the public grabbers are archived on either the [I2NDT Grabber Compendium](http://digilander.libero.it/i2ndt/grabber/grabber-compendium.htm), the [VK4YEH QRSS Grabber Aggregator](http://www.vk4yeh.com/qrss_grabber.htm), or [QRSS Plus aggregator](http://www.swharden.com/qrss/plus/). Go there to check for your signal on an appropriate grabber.

{% include links.html %}
