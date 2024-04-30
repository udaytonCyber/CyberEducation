**Samba File Server Config**
==========================

Copying files to and from a Linux server with SSH and WinSCP is certainly a possibility, but it isn't for all users. It requires extra software and a little extra know how. Most users are familiar with using Windows File Explorer to manage files. With the Samba service, we can setup file sharing over the network that will work natively with Windows.

**Configuring Samba**
-------------------

Remember to complete the rest of this lab using PuTTY or the Windows Terminal from your Windows 11 system. In previous sections, we have already installed the software packages we need for Samba. We also have already started and enabled the service. All that is left is to configure the service to meet our needs.

We want to share the Cincinnati, Managers, and Developers directories with the users we had already setup permissions for. By editing a few settings in the Samba configuration file, we can make this happen.

**Samba Configuration File**
---------------------------

The Samba configuration file is located at the path `/etc/samba/smb.conf`. This file already exists as a sample file that has a lot of configurations we do not need. The first thing we want to do is rename the existing file to make a backup. It's always a good idea to make a backup of a configuration file when making changes, just in case you need to revert.

* Rename the `smb.conf` file with the following command:




sudo mv /etc/samba/smb.conf /etc/samba/smb.bak



* Create a new file using vi:




sudo vi /etc/samba/smb.conf




The new file doesn't have any settings in it, so we will have to fill those in ourselves. The Samba configuration file always starts with a Global section. The beginning of a section is indicated by the name of the section in [brackets]. The name of the Global section is always `[global]`.

**Global Settings**
-------------------

Within the global section we can enter in settings that apply to the entire system. There are many different settings that can go here, but we are going to keep it simple for this example. We only need to specify two settings: "NetBIOS name" and "workgroup".

* Enter the global settings as follows (replace the NetBIOS name with your hostname):




[global]
netbios name  = student-vm
workgroup = workgroup




**Shared Folder Sections**
-------------------------

To create shared folders, we need to create new sections for each shared directory. The name of the section should match the folder name we want displayed to users when they connect.

* Add the following sections for the shared directories to the configuration file:




[Cincinnati]
path = /share/Cincinnati
read only = no

[Managers]
path =  /share/Managers
read only = no

[Developers]
path = /share/Developers
read only = no




**Saving and Restarting**
-------------------------

* Save the file by going to command mode and typing `wq`, then Enter.
* Create Samba user accounts for each of our users. Set the passwords to Pa$$w0rd:




sudo smbpasswd -a msmith
sudo smbpasswd -a tanderson
sudo smbpasswd -a jfallon
sudo smbpasswd -a jdenver




For our configuration changes to take place, we must now restart the services.

* Restart the services with the systemctl command:




sudo systemctl restart smb
sudo systemctl restart nmb




**Connecting and Testing**
-------------------------

If everything is configured correctly, we should be able to now connect to the Linux directories over the network with Windows File Explorer.

* Open Windows File Explorer (the folder Icon)
* In the address bar, enter the UNC path `\\<servername>` replacing `<servername>` with your Linux system hostname.
* Hit Enter.
* You will be prompted for a username and password. Login with the msmith account.
You should see three network folders.

Open each folder and attempt to make a new file or folder. Take note of which folders work and which folders do not.