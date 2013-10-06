PiWiFi
======

Using the Raspberry Pi as a router often causes usb scheduler issues due to ethernet and wifi being over USB.  This is a portable kernel module (PKM) to intelligently schedule network traffic when using the pi with both ethernet and wifi interfaces.

Hardware Requirements
=====================
Piwifi has been tested to work with the Raspberry Pi running the Raspbian OS, and with the Beaglebone Black running Ubuntu 12.04 from the onboard eMMC flash memory.  The requirements for each are listed below.

Raspberry-Pi Node:

 *  Raspberry Pi (256MB or 512MB of RAM will work)
 *  USB WiFi adapter (tested with the N150 adapter using the Ralink 5370 chipset)
 *  SD memory card (4GB minimum)

Beaglebone Black Node:

 *  Beaglebone Black
 *  USB WiFi adapter (tested with the N150 adapter using the Ralink 5370 chipset)
 *  SD memory card (4GB minimum) (used for initial imaging of the eMMC flash memory only)

Raspberry Pi Installation
=========================

1.  On the raspberry pi, run the following commands to download the piwifi project and install

        git clone https://github.com/piwifi/piwifi.git
        cd piwifi
        sudo sh install.sh

Beaglebone Black Installation
=============================

1. Download the latest Beaglebone Black Ubuntu 12.04 image: http://www.armhf.com/index.php/boards/beaglebone-black/#precise
1. Write the image to an SD memory card using the steps on the page referenced in the previous step
1. Insert the SD card into a Beaglebone Black board
1. Apply power to the Beaglebone Black
1. Login to the Beaglebone Black through an SSH session or the console using the 'ubuntu' account
1. Transfer the image to the running Beaglebone Black using SCP
1. Write the image to the eMMC flash memory using the steps mentioned in the first step here.
1. Wait for all 4 LEDs to go solid (could take several minutes)
1. Shutdown the Beaglbone Black (sudo /sbin/init 0)
1. Remove the memory card from the Beaglebone Black
1. Apply power to the Beaglebone Black
1. Login to the Beaglebone Black through an SSH session or the console using the 'ubuntu' account
1. Change the password for the 'ubuntu' account
1. Install the development tools necessary to build OLSRD and retrieve the piwifi project:

        sudo apt-get upgrade
        sudo apt-get install make gcc git
1. If installing over an SSH connection, then I recommend you install 'screen' (sudo apt-get install screen) to ensure that the installation script is not stopped prematurely if you lose connectivity.  This is optional, but I highly recommend using screen if installing over the network.  You can find more info on screen here: http://linux.die.net/man/1/screen
1. Run the following commands to download the piwifi project and install

        git clone https://github.com/piwifi/piwifi.git
        cd piwifi
        sudo sh install.sh
