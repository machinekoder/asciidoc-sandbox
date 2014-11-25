# BeagleBone Black
This guide will help you installing Machinekit on your BeagleBone Black. Throughout the whole guide it is assumend that you are using **Linux** as host system. Most steps should also work on **Mac OSX** without alterations.

If you have no Linux system installed on you computer I recommend you installing [Ubuntu](http://www.ubuntu.com/download) in [VirtualBox](https://www.virtualbox.org/). 

Alternatively you can take a look at the [BeagleBone Getting Started](http://beagleboard.org/getting-started) for instructions on flashing SD card images with other operating systems.

**Requirements**

* BeagleBone Black
* Micro SD card with 4GB or more
* Linux or Mac OSX with Unix Shell *or*
* *SSH terminal application*
* *application to flash image to SD card*

## Open Terminal
First you have to open the terminal application on your Linux installation. On most Linux disributions it is called Terminal and can be found in the start menu under System or Utilities. 

In **Ubuntu** simply type terminal in the menu.

in **Mac OSX** type Terminal in the search menu.

## Download BBB Debian image
First you have to download a recent Debian image for the BeagleBone Black. The latest release of the RCN Debian images can be found here: [BeagleBone Black - Debian Releases](http://elinux.org/Beagleboard:BeagleBoneBlack_Debian#Debian_Releases)

Download the latest **microSD/Standalone: (lxde)** image. If you have wget installed you can use for example:

    wget https://rcn-ee.net/rootfs/bb.org/testing/2014-11-19/lxde-4gb/bone-debian-7.7-lxde-4gb-armhf-2014-11-19-4gb.img.xz
    
Optionally you can check the MD5 checksum of the image after the download:

    md5sum <name of image>.img.xz
    
## Flash image to Micro SD card
