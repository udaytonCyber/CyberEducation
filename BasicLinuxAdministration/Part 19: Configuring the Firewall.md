**Part 19: Configuring the Firewall**

In this part, we will configure the firewall to allow services through it. By default, most services are blocked by the firewall to prevent unwanted access and reduce vulnerabilities.

**Listing Current Services**

Check which services are currently allowed through the firewall:




firewall-cmd --list-services




Currently, there are two services allowed: SSH and DHCP. We will leave these allowed as they are necessary for remote connections and network settings.

**Allowing Samba Service**

To allow the samba service through the firewall, we can use a predefined file or specify individual ports. Let's open the file for the samba service to view its contents:




sudo less /usr/lib/firewalld/services/samba.xml




This file contains information about the individual ports that need to be opened for the Samba service to work.

**Adding Samba Service**

Allow the samba service through the firewall using the following command:




sudo firewall-cmd --permanent --add-service=samba




The `--permanent` option sets the service to always be allowed, even after a reboot of the system. Before the service is allowed, we must reload the firewall.

**Reloading Firewall**

Reload the firewall using the following command:




sudo firewall-cmd --reload




Verify that the samba service is allowed through by running:




sudo firewall-cmd --list-services




Add the remaining services (samba-client, http, and https) in a similar manner. Be sure to reload the firewall after each addition.

**Disabling SELinux**

Linux has a kernel-level security feature known as SeLinux. To simplify our configuration process, we will disable it. This is not recommended on a production system.




sudo vi /etc/selinux/config




Change the line `SELINUX=enforcing` to `SELINUX=disabled`. Double-check for typos and save the file.

**Rebooting System**

Reboot the system with:




reboot




Once the system reboots, you can close the console window. We will complete the rest of this lab remotely from our Windows 11 system.