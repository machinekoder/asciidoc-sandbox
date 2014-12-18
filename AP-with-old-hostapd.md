# Getting rtl8188eu and rtl8192 to work

## Prepare environment
First we need to install a suitable build environment

    sudo apt-get install build-essential linux-headers-$(uname -r)

## Install 8188eu driver and hostapd

    git clone https://github.com/lwfinger/rtl8188eu.git
    cd rtl8188eu
    make
    sudo make install
    cd hostapd-0.8
    cp defconfig .config
    make
    sudo make install

## Install 8192cu driver
http://forum.ubuntuusers.de/topic/wlan-stick-524440/3/#Realtek-rtl8192cu-s-Treiber-fuer-12-04-4-12-04-5-und-14-04-fuer-Kernel-3-11-und-3-13

    git clone https://github.com/pvaret/rtl8192cu-fixes.git
    sudo dkms add ./rtl8192cu-fixes
    sudo dkms install 8192cu/1.9




apt-get source hostapd
sudo apt-get build-dep hostapd
git clone https://github.com/pritambaral/hostapd-rtl871xdrv.git
cd wpa-1.0

patch -Np1 -i ../hostapd-rtl871xdrv/rtlxdrv.patch
cp ../hostapd-rtl871xdrv/driver_rt* src/drivers/
cp ../hostapd-rtl871xdrv/.config hostapd/