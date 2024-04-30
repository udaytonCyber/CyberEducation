**Package Managers**
=====================

When installing Linux operating systems, there are many software applications that come pre-installed. Sometimes it's necessary to install additional software after installation. There are three methods for installing software on a Linux system: using a package manager, installing from a single package, and compiling source code.

A **package manager** is a special program that comes with each Linux distribution. It allows you to install and manage the latest software from Internet repositories. The choice of distribution determines which package manager you'll use. For example:

* Ubuntu and Debian use Advanced Package Manager (APT)
* SUSE Linux uses Yet Another Package Manager (yast)
* Red Hat Enterprise Linux based systems use Yellow Dog Updater/Modified (yum) or Dandified YUM (dnf)

**Software Repositories**
-------------------------

A software repository is a location on the Internet that contains a collection of software programs and shared libraries. There are often several "mirror" sites that offer copies of available software.

All package managers work similarly, but have different commands. Since we're working with Oracle Linux 9, we'll focus on the dnf/yum package manager.

**Advantages**
-------------

Package managers have many advantages:

* Simple to use
* Help you keep track of what's installed and what's available
* Always install the latest version provided by the distribution

When using a package manager to install software, dependencies are found that may be required and are installed as well. Dependencies are other software programs or shared libraries that are needed to run a piece of software.

**Cons**
-----

Package managers have some cons:

* Only allow you to download the latest version of the software
* Can only use them to download software made available through the distribution's repositories

The YUM package manager can be controlled using the command line with the `yum` command. There are several options that allow you to install, update, and get information about software on your system or available through the repositories.

**Getting Information**
----------------------

To see information about installed packages, run:




sudo yum info firefox




This will show you information about any installed packages with that name, as well as list any available packages in the repository. If no package is installed, it will only show what's available.

**Updating Software**
--------------------

To update to the latest version of a software package, run:




sudo yum update firefox




The package manager will search for dependencies and include them if necessary. In this case, there were no dependencies.

**Installing Software**
----------------------

To install a database using YUM, run:




sudo yum info postgresql




This will show you information about the available packages. To install the PostgreSQL database, run:




sudo yum install postgresql




Yum also gives us the ability to install groups of software to perform specific functions.

**Installing Groups**
---------------------

To see a list of available groups, run:




sudo yum group list




This will show you Environment Groups and Available Groups. To install Development Tools, run:




sudo yum groupinstall "Development Tools"




Once the installation is complete, find out which version of the `gcc` compiler was installed.