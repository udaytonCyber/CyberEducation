**Part 12: Working with Packages**
==============================

Package managers are a very convenient and easy way to install software, but sometimes they don’t have the exact packages you need. Perhaps you need an older version of a piece of software or perhaps the software you are installing comes from a 3rd party and is not available through the package manager. In these cases, we can install the packages manually.

A **software package** is a special type of archive file format that contains everything you need to install a piece of software. This includes the binary files, executable files, configuration files, and scripts for running the installation. Most software developers will create these software packages to make it easier for customers to obtain and install their software.

Every different operating system has their own format of packages. If you are a Windows user, you may be familiar with the MSI software package. Apple Mac and iOS devices use a PKG file. Android uses an APK file format.

In Linux there are a few different package formats depending on your distribution, but the most popular are DEB files for Debian-based distros such as Ubuntu, and RPM files for Red Hat-based distros such as CentOS, Oracle Linux, Rocky Linux, and Alma Linux. These archive files can be identified by a file extension. In the case of RPMs in Oracle Linux 9, the files will have a `.rpm` file extension.

**Obtaining Software Packages**
-------------------------------

We can obtain software package files from several sources. Many software vendors will have you download them from the web. They can also be found in the distribution’s online repository. You can also obtain them on physical media such as a CD or DVD ROM.

**Managing and Installing Software Packages**
--------------------------------------------

We can manage, install, update, and find information about software packages on our system using the `rpm` command. One of the features of this command is it allows us to query what software is currently installed on our system.

### Querying Installed Packages
-------------------------------

* Run the following command: `sudo rpm -qa`
This will list off all the currently installed software packages on the system.
* Search for a package by running the following command: `sudo rpm -q nano`
This will bring back the version information if the package is installed.

**Removing Software Packages**
---------------------------

To remove this software package from the system, use the `-e` option to “erase” the software from the system:

* Run the following command: `sudo rpm -e nano`

We will reinstall this package manually after downloading it from the internet.

### Downloading and Installing a Package

In order to install this package, we have to tell the file system to let it be executable. We do that with the following command:




chmod +x nano-5.6.1-5.el9.X86_64.rpm




We then can install the package with the command:





sudo rpm -ivh nano-5.6.1-5.el9.X86_64.rpm




Verify that the package has installed with:




sudo rpm -q nano


