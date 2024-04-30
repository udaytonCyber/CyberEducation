**Linux Services**
==================

Services in Linux (sometimes referred to as Daemons) are system processes (or groups of processes)
that work in the background waiting to be used. When in use, they perform essential tasks that provide
a specific functionality to the system.

Some examples of services include:
* Network Service – Provides network communication for the system.
* sshd – Provides secure access to the command shell from a remote computer.
* firewalld – Provides packet filtering for security.
* samba – Provides file sharing over a network connection.
* Apache (httpd) – Provides Web communication over http protocol.

**Systemd**
------------

In modern Linux systems, services are controlled through a subsystem known as systemd. When a
system boots, systemd calls what are known as unit files to start services. These unit files act as small
applications that start the processes related to the services installed.

A systems administrator can manually control services through a systemd command `systemctl`. With this
command we can:
* Start: Run the service.
* Stop: Halt the service.
* Restart: Reload the service with any changes made to configuration files.
* Enable: Set the service to start at boot.
* Disable: Prevent the service from starting at boot.

**Viewing Services**
-------------------

We can view services currently installed on the system using the following command:




systemctl list-units --type service




This list shows the names of the services, a description of what the service does, and whether it’s active
and running or not.

**Checking Service Status**
----------------------------

We can find out the status and more information from a single service using the `status` option.
* Run the following command to check the status of the "firewalld" service:




systemctl status firewalld




This output shows if the service is enabled, active (running), and how long it’s been running for. It will also display the last few lines written to the system log file related to this service.

**Disabling Services**
----------------------

When a service is disabled, that means the service is set to not start at boot. Sometimes we may want
to manually disable services only when needed.
* Run the following command to disable sshd:




sudo systemctl disable sshd




What is happening when we disable a service is a symbolic link is removed from the directory systemd uses during boot.

**Enabling Services**
----------------------

If we wanted a service to start at boot, we must enable it to do so.
* Run the following command to enable sshd:




sudo systemctl enable sshd




In this case, systemd created a symbolic link to the sshd unit file to start at boot.

**Stopping and Starting Services**
--------------------------------

Disabling and enabling does not change the current state of the service. To do this, we must use the options stop and start.
* Stop the network service using the following command:




systemctl stop network




You will not get any output from this command, but you can check the state of the service:




systemctl status network




You can now see the active state is inactive (dead). You may have also noticed you lost network connectivity. With this service stopped, network communications no longer work.

* Start the network service again with the following command:




sudo systemctl start network




Check the status of the service again. It should show as active.

**Restarting Services**
----------------------

When we are installing and configuring new services, we often must make changes to configuration files.
These configuration files are only read by the services when they start. Since most services start at boot,
if we made a change, it would not take effect until we restarted the system. The good news is that this
is not necessary as we can use the `restart` option to quickly reload a service with the new configuration.
* Restart the network service using the following command:




systemctl restart network


