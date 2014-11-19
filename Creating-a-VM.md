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