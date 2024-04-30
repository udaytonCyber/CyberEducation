**Part 18: Installing/Updating Software for Network Services**

In this part, we will install and update software packages that provide network services on our Linux system. We will use the YUM package manager to install the following services:

* Firewalld (packet filtering firewall security)
* Samba (file sharing using SMB protocol)
* Samba-client (allows clients to connect to Samba shares)
* Apache (web service for HTTP and HTTPS protocols)

**Installing Services**

Use a single command to install all the services:




sudo yum install firewalld samba samba-client httpd




This will download and install the necessary packages.

**Starting and Enabling Services**

Start and enable each of the services using the following commands:

* Smb (Samba service):
	+ Start: `sudo systemctl start smb`
	+ Enable: `sudo systemctl enable smb`
* Nmb (NetBIOS name service):
	+ Start: `sudo systemctl start nmb`
	+ Enable: `sudo systemctl enable nmb`
* Httpd (Apache web server):
	+ Start: `sudo systemctl start httpd`
	+ Enable: `sudo systemctl enable httpd`

**Checking Service Status**

Check the status of each service to ensure they are running using the following commands:

* Smb:
	+ Check status: `sudo systemctl status smb`
* Nmb:
	+ Check status: `sudo systemctl status nmb`
* Httpd:
	+ Check status: `sudo systemctl status httpd`

By installing and enabling these services, we can provide file sharing (Samba), web services (Apache), and packet filtering firewall security (Firewalld) on our Linux system.