## Step 1: Install VirtualBox Guest additions
See http://www.binarytides.com/virtualbox-guest-additions-debian-wheezy/

## Step 2: Add the machinekit user to sudoers

    usermod -aG  sudo,kmem machinekit
    sudo su -c 'echo -e "# No sudo password for machinekit user\nmachinekit ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/90-machinekit'

## Step 3: Enable autologin
    sudo nano /etc/lightdm/lightdm.conf
Edit

    [SeatDefaults]
    #autologin-user=
    #autologin-user-timeout=0

## Step 4: Install tilda
    sudo apt-get install tilda
    mkdir -p ~/.config/autostart/
    nano ~/.config/autostart/tilda.desktop
With following contents:

    [Desktop Entry]
    Type=Application
    Exec=tilda
## Step 5: Keyboard Layout switching
Add your keyboard layouts to the file `/etc/default/keyboard`. Then run

    udevadm trigger --subsystem-match=input --action=change

After that you can add the LXDE "Keyboard Layout Switcher" applet the LXDE panel.