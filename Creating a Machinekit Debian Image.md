### step 1: Download BBB Debian image
Download latest image from http://elinux.org/Beagleboard:BeagleBoneBlack_Debian#Debian_Releases
and check the md5 sum

### step 2: extract image files
	unxz <compressed image file>

### step 3: flash image file to SD card
Use dmesg to check for the name of the SD card partition then flash 
the image file:
e.g.

	sudo dd bs=4M if=bone-debian-7.6-lxde-armhf-2014-08-05-4gb.img of=/dev/mmcblk0

Note: you may need to flash a new bootloader using the eMMC-flasher 
images

### step 4: connect to the BBB using SSH
Use you favorite terminal application to connect to the BBB:
	ssh root@beaglebone.local

### step 5: add a new user
To make Machinekit work properly we need a new user:
	adduser machinekit
	usermod -aG  sudo,xenomai.kmem machinekit

Remove the sudo password by adding a new entry to sudoers.d:
	sudo su -c 'echo -e "# No sudo password for machinekit user\nmachinekit ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/90-machinekit'

Now change the root user password to improve security:
	passwd

### step 6: change the hostname
You may want to change the hostname of the image. Change beaglebone 
in the following two files with the name you want.
	nano /etc/hostname
	nano /etc/hosts

Reboot to apply the changes.

### step 7: logout and login as new user
	exit
	ssh machinekit@beaglebone.local

### step 7: install Machinekit
Now we need to install the Machinekit packages:
see http://www.machinekit.io/docs/packages-debian/
additional steps:

	sudo apt-get install linux-image-xenomai

### step 8: deactivate all unneeded capes
We should check all the capes that are loaded by default (can change 
between images) and deactivate all that are not necessary. You 
can check the loaded capes with:

	cat /sys/devices/bone_capemgr.*/slots

To deactive loading of specific cape at boot you need to edit the 
uEnv.txt:

	sudo nano /boot/uEnv.txt
### step 9: change SSH banner message
The default banner message on the BBB image is located at 
/etc/issue.net you can edit by running:
	sudo nano /etc/issue.net

### step 10: install AP-Hotspot
To make it possible to connect the BBB using the a AP Wifi network 
we have to install the AP-Hotspot script:

	mdkir bin
	cd bin
	git clone https://github.com/strahlex/AP-Hotspot.git
	cd AP-Hotspot/
	sudo apt-get update
        sudo apt-get install libnotify-bin iw dnsmasq
	sudo make install

### step 11: Additional modifications
We may need a folder in the home directory of the machinekit user for 
gcode files:
	mkdir ~/nc_files

It is possible to rename the FAT32 partition that is mounted when the 
BBB is connected to a computer using USB. This may be done with any 
suitable application.
