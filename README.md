# NFCRFID Controller (Adafruit PN532)

##### Table of Contents  

- [Introduction](#introduction-using-a-system-diagram)
- [Bill of Materials/Budget](#bill-of-materials-budget)
- [Time Commitment](#time-commitment)
- [Raspberry Pi Headless Setup](#Raspberry-PI-Headless-Setup)
- [Mechanical Assembly](#mechanical-assembly)
- [PCB / Soldering](#pcb---soldering)
- [Power Up](#power-up)
- [Unit Testing](#unit-testing)
- [Production Testing](#production-testing)



## Introduction

With the introduction of NFC, contactless payment and data transfer has become more popular over the last decade. This project is intended to deal with managing item loaning/inventory over NFC but can be used for various other projects as well. 

The modular project itself deals with 4 major components: a Raspberry Pi 2 or 3, a PCB, a NFC Controller (Adafruit PN532) and a 3D-printed enclosure. The Raspberry Pi acts as a computer so that data can be entered to or retrieved from the PN532 when an NFC device/card has been detected. To connect the 2 devices together, a PCB needs to be printed with other soldered on components. In terms of communication between the two devices, it uses a I2C protocol that has a serial data line and clock line to manage data transmission. Enclosing the entire project is a self-design 3D printed case. The case allows easy access for users to troubleshoot any problems encountered along the way of this project.



## Bill of Materials/Budget






## Time Commitment

The overall time needed to complete this project will depend on the approach taken to complete it. It will mainly depend on how the PCB and 3D printed enclosure are printed and delivered. Getting it printed at a local makerspace such as a Library or Prototype lab maybe more convenient but may yield long wait times due to limited machines. Getting the PCB and enclosure printed through a reputable company would be faster, but may also introduce long delivery times if it gets held back at customs.

In terms of assembly, setup and troubleshooting the project should take approximately 2-3 hours to complete.



## Raspberry PI Headless Setup
Use the following guide to setup your raspberry PI using the Headless Setup Method(No Display Required)

<b>Equipment Required:</b> Computer, Ethernet Cable, RPI 2 or 3, USB-Ethernet (if required)<br>
<b>Required Downloads:</b> Etcher, Bonjour, Putty 

<b>Guide Coverage:</b>
-	How to Image a MicroSD Card
-	Headless Wi-Fi / Ethernet
-	Direct Ethernet Connection Setup
-	Connect via SSH using Putty

<b>*Important Steps to Follow After Inital Setup:*</b>

Additional Step while in `sudo rasp-config` after enabling VNC viewer, enable the I2C interface as well. This will allow the raspberryPi to communicate with the NFC Controller. Exit and then return to the main terminal.

Fetch the list of updates for RPI using the command: `sudo apt-get update` and then `sudo apt-get upgrade`. Enter `Y` when prompted to do to begin the install of the updates for the Raspberry Pi. The time to complete the download and install will vary depending on the Internet download speeds.

When the downloads are completed, down the libNFC repository by running the command:<br>

`apt-get install libnfc-bin libnfc-examples libnfc-pn53x-examples`

Configure the configuration file by running the following command: <br></br>
`sudo nano /etc/nfc/libnfc.conf`

Add the following to the bottom of the file:
```
device.name = “Pn532”
device.connstring = “pn532_i2c:/dev/i2c-1”
```
<br></br>

Here is an alternative Setup Method(With HDMI) if you cannot get the headless setup to work: https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up

<br></br>

*Important Note: When waiting for something to install, work on the other portions of the project to cut down the time to complete it.*



## Mechanical Assembly








## PCB / Soldering







## Power Up







## Unit Testing








## Production Testing





