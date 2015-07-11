# Starting a Machinekit configuration at boot
With Systemd it is pretty easy to start a Machinekit configuration right after boot. The configuration in this tutorial is called _example_, you may replace all appearances to match with the name of your Machinekit configuration. The example configuration in this tutorial is started using the python launcher library.

On **Debian Wheezy** you need to update systemd from the backports. See the instructions for [AP-Hotspot](https://github.com/strahlex/AP-Hotspot#install) for details.
### Service configuration
First we need to create a new Systemd service:

        sudo nano /etc/systemd/system/example.service

With the following content:

        [Unit]
        Description=Starts my Uber-awesome Machinekit configuration
        After=syslog.target network.target ap-hotspot.service
        [Service]
        Type=simple
        ExecStart=/usr/bin/python /home/machinekit/projects/Example/run.py
        User=machinekit
        LimitMEMLOCK=33554432
        [Install]
        WantedBy=multi-user.target

**After:** Take a close look at the _After_ parameter. It is configured to start after the ap-hotspot service. You may alter this line if you do not have a wireless access point.

**ExecStart:** The _ExecStart_ parameter is configured to start a python run script. You may alter this line for your configuration.

**User:** Insert the user configured to start Machinekit configurations.

**LimitMEMLOCK:** Prevents 'Cannot allocate memory' errors from happening.

### Starting the service
The Systemd service is now ready to be configured:

        sudo systemctl daemon-reload
        sudo systemctl start example.service

Wait a few seconds and check the status of the service:

        sudo systemctl status example.service

After you have approved that everything works fine its time to enable the service to be started at boot:

        sudo systemctl enable example.service

### Reboot
Now it is time to reboot the system to test configuration:

        sudo reboot

Take a cup of coffee and cross your fingers...

### Also Useful

If you want to disable the service again:

        sudo systemctl disable example.service

Stopping the service:

        sudo systemctl stop example.service
