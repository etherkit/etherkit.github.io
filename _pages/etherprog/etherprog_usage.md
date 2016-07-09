---
title: EtherProg Usage Guide
keywords: etherprog, hardware
summary: "How to use EtherProg"
sidebar: etherprog_sidebar
permalink: etherprog_usage
folder: etherprog
---

## Installing AVRDUDE

In order to use EtherProg, you will need to first install the AVRDUDE utility software. Instructions for each major operating system follows.

### Windows

In order to use AVRDUDE on Windows, you will need to install the [WinAVR](http://winavr.sourceforge.net/index.html) package, which will also give you the AVR GCC tools and an integrated development environment, if you choose to write or modify AVR code.

Go to the WinAVR download site [here](http://sourceforge.net/projects/winavr/files/WinAVR/) and click on the folder name with the latest date. Click on WinAVR-xxxxxxxx-install.exe (where xxxxxxxx is the software release date) to download the WinAVR installer to your PC. Execute the installer file you just downloaded and accept all of the defaults to install WinAVR to your PC.

### OS X

There are a few different options for OS X users, but perhaps the simplest to get working is [CrossPack](http://www.obdev.at/products/crosspack/index.html) (which does not require the cumbersome Xcode). It will install AVRDUDE, plus the other command line tools needed to build AVR GCC code.

Go the the CrossPack download site [here](http://www.obdev.at/products/crosspack/download.html) and click on CrossPack-AVR-xxxxxxxx.dmg (where xxxxxxxx is the software release date) to download the disk image to your Mac. Execute the disk image to launch the installer and accept all of the defaults to install CrossPack to your Mac.

### Linux

Most Linux distributions have AVRDUDE available in their software repositories. In Ubuntu and other Debian-based distributions (such as Debian, Linux Mint, etc.) you can type the following at a command prompt to install AVRDUDE:

```shell
$ sudo apt-get install avrdude
```

## A Quick Tutorial

The first thing that you will need to do to flash firmware onto an AVR microcontroller is to connect EtherProg to your PC and to the target microcontroller's ISP header. Any common USB A-B cable can be used for the PC connection. The 6-conductor ribbon cable on EtherProg is used to connect it to the target device. The red stripe on the cable is aligned towards the marked pin 1 on the target ISP header (it may be indicated on the PCB or may just be a square PCB pad).

In many circumstances, you will need to have EtherProg provide DC power to the target microcontroller during programming since the main power of the device is not connected. If this is the case, make sure jumper JP1 is on the header. If your target already has power provided from its own source, remove the jumper from JP1.

For this example, let us assume that you need to write to the flash memory of an AVR. Atmel AVR microcontrollers are programmed using files in the [Intel HEX format](http://en.wikipedia.org/wiki/Intel_HEX) (usually with the extension .hex). Open up a command terminal and navigate to the directory containing the HEX file you wish to flash.

AVRDUDE has many command line options, but let's focus on the bare necessities. The first option is -c, which specifies the type of programmer being used. In our case, we will want to specify usbtiny.

```shell
-c usbtiny
```

Next, we need to specify which type of device we will be writing to, which is accomplished with the -p flag. For this example, let's pretend that we are writing new firmware to OpenBeacon, which uses an ATtiny85. The command line flag for this is t85. You can find the full list of device flags [here](http://www.nongnu.org/avrdude/user-manual/avrdude_4.html#Option-Descriptions) for the specific one you may need.

```shell
-p t85
```

Finally, we need to tell AVRDUDE which HEX file to use, and what to do with it. This is accomplished with the -U flag. There are three parameters that need to be passed with the flag; each separated with a colon. The first is the type memory that we will be writing to. In this case, it's flash memory, so the parameter is flash. Next is the type of operation we want to perform with that memory (reading, writing, or verifying). We wish to write the HEX file, so we pass along w. Last is the actual filename to be written to memory. In this case, we'll say it's OpenBeacon.hex. So the entire option looks like this:

```shell
-U flash:w:OpenBeacon.hex
```

We can put those parameters all together in any order on the command line call to AVRDUDE.

```shell
$ avrdude -c usbtiny -p t85 -U flash:w:OpenBeacon.hex
```

If the operation was successful, you'll see something like this:

```shell
avrdude: AVR device initialized and ready to accept instructions

Reading | ################################################## | 100% 0.01s

avrdude: Device signature = 0x1e930b
avrdude: NOTE: FLASH memory has been specified, an erase cycle will be performed
         To disable this feature, specify the -D option.
avrdude: erasing chip
avrdude: reading input file "OpenBeacon.hex"
avrdude: input file OpenBeacon.hex auto detected as Intel Hex
avrdude: writing flash (7838 bytes):

Writing | ################################################## | 100% 5.27s



avrdude: 7838 bytes of flash written
avrdude: verifying flash memory against OpenBeacon.hex:
avrdude: load data flash data from input file OpenBeacon.hex:
avrdude: input file OpenBeacon.hex auto detected as Intel Hex
avrdude: input file OpenBeacon.hex contains 7838 bytes
avrdude: reading on-chip flash data:

Reading | ################################################## | 100% 4.10s



avrdude: verifying ...
avrdude: 7838 bytes of flash verified

avrdude: safemode: Fuses OK

avrdude done.  Thank you.
```

If you are using a Linux distribution and receive a permission error, you will either need to issue the above command under sudo or create a udev rule so that you will not need to use sudo each time. See the section below this one for details.

It is also common to have the need to do other things, such as write files to EEPROM or configure the fuses in the AVR. Consult the [AVRDUDE page](http://www.nongnu.org/avrdude/user-manual/avrdude_4.html#Option-Descriptions) on command options for full details on how to accomplish this.

## Linux _udev_ Rules

Many Linux distributions will require you to add a rule to the udev system in order to have non-superuser access to EtherProg via USB. The following instructions are written specifically for Ubuntu, but should be applicable for most other distributions as well.

All of these commands are issued via terminal, so open one up to get started.

We will create a new rules file with the following command:

```shell
$ sudo nano /etc/udev/rules.d/10-etherprog.rules
```

Copy and paste the following text into the first line of the nano text editor:

```shell
SUBSYSTEMS=="usb", ATTRS{idVendor}=="1781", ATTRS{idProduct}=="0c9f", GROUP="adm", MODE="0666"
```

Press Ctrl-O to save the rules file, then Ctrl-X to exit. Finally, we need to restart udev, so issue the following command in the terminal:

```shell
$ sudo restart udev
```

If your EtherProg is currently plugged in, disconnect it then connect it again. You should now have non-superuser access to EtherProg via the client program.

## For More Information

Please see the [AVRDUDE documentation website](http://www.nongnu.org/avrdude/user-manual/avrdude.html) for full details on how to use the utility.



{% include links.html %}
