**Remote Server Management with SSH**
===============================

For the rest of this Lab assignment, we will be using the Windows 11 system. You can log into the Windows 11 system with the "student" account and password, student.

Remote server management is not only very convenient; these days it's almost necessary. Many datacenters have gone to light's out management, meaning they have little to no staff on site. Perhaps the servers you manage are co-located at another site altogether. Even more likely is that the servers you manage are hosted in the Cloud, which could be located anywhere in the world. Without remote management it would be difficult to keep up on important maintenance tasks.

**Secure Shell (SSH)**
-------------------

There's good news! Linux systems have an easy and secure method of accessing the command shell from just about any computing device. Secure Shell (SSH) is a network service that can be run on any Linux system and is often enabled by default. It uses an encrypted protocol to hide the commands being sent across the network from a would-be hacker. You can use SSH from any Windows, Linux or macOS command terminal or install a small program such as PuTTy on any Windows workstation.

**Security Considerations**
-------------------------

While SSH is secure, it's advised to keep access to the service behind a VPN and Firewall. Opening this service on the public internet will invite brute force attacks. A strong password, using encryption keys, or disabling the root account will help to mitigate these attacks, but it does create unnecessary traffic on your network.

**Connecting with PuTTy**
-------------------------

In this section, we will be using two pieces of software to connect our Windows 11 system to our Linux system. If you don't already have these installed on your system, you can download them from the following sites:

* [PuTTY](http://www.putty.org)
* WinSCP - https://winscp.net

As an alternative to PuTTy, you can use the new Windows Terminal, which now has native SSH client capabilities built in.

**Connecting with SSH**
-------------------------

Open the Windows Terminal and type:




ssh student@hostname




where `hostname` is the hostname you chose for your machine. Where `student` is the username of the account you are connecting as.

**Downloading Files**
-------------------

Next, we want to download some files for our website:

* Download the Website zip file to your Desktop.
* Right click the file and choose extract all.
* Click the button to extract the files.

Using WinSCP we can use SSH to copy these files over to the Developers directory on the Linux server.

**WinSCP**
---------

Double click the WinSCP icon. In the hostname field, enter in the hostname of the Linux system. Since we are copying these to the Developers directory, we need to log in as someone who has access to that directory. Use the tanderson account for the username and password. Click Login.

Click yes to accept the security warning.

WinSCP has two directory windows. The window on the left is the Local system and the window on the right is the Linux system.

* On the left-hand side, click the folder with the arrow up to move up a level. Then choose the Desktop and browse to the folder `C:\Users\user\Desktop\Website files\Website`
* On the right-hand side, click the folder with the arrow up twice to get the root directory (`/`), then browse to the `/share/Developers` directory.

Click and drag the images folder and index.html file from the left to the right. The files have now been copied and are ready to be used to setup a website.