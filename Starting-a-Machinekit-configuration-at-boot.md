# Starting a Machinekit configuration at boot
With Systemd it is pretty easy to start a Machinekit configuration right after boot. The configuration in this tutorial is called _example_, you may replace all appearances to match with the name of your Machinekit configuration. The example configuration in this tutorial is started using the python launcher library.

First we need to create a new Systemd service:

        sudo nano /lib/systemd/example.service

With the following content:

        [Unit]
        Description=Starts the UNIPRINT-3D machinekit configuration
        After=syslog.target network.target ap-hotspot.service
        [Service]
        Type=simple
        ExecStart=/usr/bin/python /home/machinekit/projects/Example/run.py
        User=machinekit
        [Install]
        WantedBy=multi-user.target

**After:** Take a close look at the _After_ parameter. It is configured to start after the ap-hotspot service. You may alter this line if you do not have a wireless access point.

**ExecStart:** The _ExecStart_ parameter is configured to start a python run script. You may alter this line for your configuration.

**User:** Insert the user configured to start Machinekit configurations.

Now we need to create a symlink:

        sudo ln /lib/systemd/example.service /etc/systemd/system/example.service

The Systemd service is now ready to be configured:

        sudo systemctl daemon-reload
        sudo systemctl start example.service

Wait a few seconds and check the status of the service:
        sudo systemctl status example.service

After you have that everything works fine its time to enable the service to be started at boot:

        sudo systemctl enable example.service