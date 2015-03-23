### step 1: Download BBB Debian image
Download latest image from http://elinux.org/Beagleboard:BeagleBoneBlack_Debian#Debian_Releases
and check the md5 sum

    wget <url>
    md5sum <name of image>.img.xz

### step 2: flash image file to SD card
**WARNING: Be careful when typing these commands**

Use **dmesg** to check for the name of the SD card partition then flash 
the image file. Flashing to the wrong device can result in data loss.

Reconnect your SD card reader with the SD card inserted and type the following:

    dmesg | tail

You should see something mentioning `/dev/sdX` or `/dev/mmcblkX`. This is the name of your SD card device.

Extract the image file

    unxz <name of image>.img.xz

Flash the image

    sudo dd bs=4096k if=<name of image>.img of=/dev/<device> oflag=direct

**NOTE:** if you use the SD card image you may want to **resize** it to use the whole SD card. You can use [GParted](http://gparted.org/) for this purpose.

#### Alternative with progress bar
For the following commands you need the tool `pv` installed. On Debian or Ubuntu this can be done with `sudo apt-get install pv`

For 2GB images:

    xz -dc <name of image>.img.xz | pv -s 1800000000 | sudo dd bs=4096k iflag=fullblock of=/dev/<device> oflag=direct


For 4GB images:

    xz -dc <name of image>.img.xz | pv -s 3880000000 | sudo dd bs=4096k iflag=fullblock of=/dev/<device> oflag=direct

### step 3: insert SD card and boot
Insert the SD card into your BBB and wait for the device to boot. The lights will be indication what your device is doing. 
* **No lights** means something went wrong (or your device is not powered). 
* **Randomly blinking lights** mean your device is doing something (good sign). 
* **Running lights** mean the SD card content is being flashed to eMMC. 
* **Four flashing lights** mean that you tried flashing a 4GB image to a BBB older than RevC.

If you want to connect to your BBB over **Ethernet** make sure you connect it to a DHCP server **before booting**.

**NOTE:** If the image is not booting you may need to flash a new bootloader using the console eMMC-flasher images. (usually happens with older RevB boards)

### step 4: connect to the BBB using SSH
Use you favorite terminal application to connect to the BBB:
	
        ssh root@beaglebone.local

**NOTE:** On **Windows or Mac** you may need to enter the IP address of the BBB instead of the hostname `beaglebone.local`. If you are connected over USB this is `192.168.7.2`

### step 5: add a new user
To make Machinekit work properly we need a new user:

	adduser machinekit
	usermod -aG  sudo,xenomai,kmem machinekit

Remove the sudo password by adding a new entry to sudoers.d:

	sudo su -c 'echo -e "# No sudo password for machinekit user\nmachinekit ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/90-machinekit'

Now change the root user password to improve security:

	passwd

### step 6: change the hostname
You may want to change the hostname of the image. Change `beaglebone` 
in the following two files with the name you want using the [nano](http://www.nano-editor.org/) editor.

	nano /etc/hostname
	nano /etc/hosts

Reboot to apply the changes.

	reboot

### step 7: logout and login as new user

	ssh machinekit@beaglebone.local

### step 7: install Machinekit
Now we need to install the Machinekit packages.
Follow the BeagleBone steps at [Machinekit Debian Packages](http://www.machinekit.io/docs/packages-debian/). Make sure to install the correct Linux kernel image:

	sudo apt-get install linux-image-xenomai.beaglebone-omap

### step 8: deactivate all unneeded capes
We should check all the capes that are loaded by default (can change 
between images) and deactivate all that are not necessary. You 
can check the loaded capes with:

	cat /sys/devices/bone_capemgr.*/slots

To deactive loading of specific cape at boot you need to edit the 
´uEnv.txt´:

	sudo nano /boot/uEnv.txt

For many Machinekit configurations you will need to disable the HDMI cape. This can be done by uncommenting the following command:

    cape_disable=capemgr.disable_partno=BB-BONELT-HDMI

### step 9: change SSH banner message
The default banner message on the BBB image is located at 
´/etc/issue.net´ you can edit by running:

	sudo nano /etc/issue.net

### step 10: disable SSH DNS reverse checking
The SSH DNS reverse checking feature makes the SSH login slower. As we use the BBB in an internal network only we can deactivate the reverse checking and speed things up.

        sudo su -c 'echo -e "UseDNS no" >> /etc/ssh/sshd_config'

### step 10: WiFi
If you want to use you BBB in combination with a WiFi network please follow these steps.

#### Infrastructure: wicd-curses
wicd-curses is ncurses based graphical terminal user interface to connect to (wireless) networks. You can install it by running following commands:

       sudo apt-get update
       sudo apt-get install wicd-curses

To configure your wireless network run `wicd-curses` and follow the on screen instructions.

#### Access-Point: Install AP-Hotspot
To make it possible to connect the BBB using the a AP Wifi network 
we have to install the AP-Hotspot script:

	mkdir bin
	cd bin
	git clone https://github.com/strahlex/AP-Hotspot.git
	cd AP-Hotspot/
	sudo apt-get update
	sudo apt-get install libnotify-bin iw dnsmasq
	sudo make install

I can recommend the WiPi USB dongle from element14 or any other USB wifi adapter with the same chipset.
**NOTE:** For some reason the *EDIMAX EW-7811UN Wireless USB Adapter* dongle works only with a Nexus 7 as client

### step 11: Additional modifications
We may need a folder in the home directory of the *machinekit* user for 
gcode files:

	mkdir ~/nc_files

It is possible to rename the *FAT32* partition that is mounted when the 
BBB is connected to a computer using USB. This may be done with any 
suitable application.

Starting the a Machinekit configuration at boot is also possible [Starting-a-Machinekit-configuration-at-boot](https://github.com/strahlex/asciidoc-sandbox/wiki/Starting-a-Machinekit-configuration-at-boot)