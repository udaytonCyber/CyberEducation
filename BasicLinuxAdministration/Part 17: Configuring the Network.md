**Part 17: Configuring the Network**

In this part, we will learn how to configure our server's network settings and provide services over the network to client workstations.

**Setting up User Accounts**

Before configuring the network, let's set up some user accounts:

* Create the following user accounts with password "Paw0rd" each:
	+ Terry Anderson (tanderson)
	+ Mike Smith (msmith)
	+ John Denver (jdenver)
	+ Jimmy Fallon (jfallon)

**Adding Users to Groups**

Add the users to their respective groups:

* Group Name: Cincinnati
	+ Members: msmith, tanderson, jdenver, jfallon
* Group Name: Managers
	+ Members: msmith, jfallon
* Group Name: Developers
	+ Members: tanderson, jdenver

**Creating Directories and Setting Permissions**

Create the following directories with permissions for their respective groups:

* /share/Cincinnati (read, write, execute)
* /share/Managers (read, write, execute)
* /share/Developers (read, write, execute)

**Configuring Network Settings**

We will manually set our network settings to a static IP address instead of using DHCP. Find the network adapter's general information by running:




nmcli d show




Take note of the following settings:

* GENERAL.DEVICE: ensXXX (ethernet adapter)
* IP4.ADDRESS: 192.168.27.31/24
* IP4.GATEWAY: 192.168.27.1
* IP4.DNS: 10.27.3.2 & 10.25.3.2

**Using Network Manager TUI**

Start the Network Manager TUI:




nmtui




Edit a connection, then select the ethernet adapter and edit its settings:

* Set IPv4 configuration to Manual.
* Add an IP address: 192.168.27.31/24.
* Set Gateway: 192.168.27.1.
* Add DNS servers: 10.27.3.2 & 10.25.3.2.

**Setting System Hostname**

Set a unique hostname, such as `<username>-lin1`, where `<username>` is your login username (e.g., "user-lin1").

**Applying Network Settings**

Stop and start the network card:




sudo ifdown ens192
sudo ifup ens192




Verify that the settings were applied by checking the "inet" address of your ethernet adapter with `ifconfig`.

**Verifying Connection**

Try to ping google.com to verify that the connection is working.