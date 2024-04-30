**Installing from Source Code**
================================

Software packages and package managers do make installing and managing software easy for a systems administrator, but they are not always an option. Packages require the software developer to take time to package everything and create scripts to install, and package managers require testing and approval from the distribution team. These processes take time and sometimes are simply not available.

**Open Source Software**
------------------------

A lot of software for Linux is also Open Source, meaning that the code is freely available for you to download and customize. It would be much more difficult to change software after it has been compiled and packaged for distribution.

**Compiling and Installing Source Code**
-----------------------------------------

In these situations, we can take the source code for the application and compile and install the software ourselves. Source code is the original programming code written with a human-readable programming language such as C++, C#, or Java. For the operating system to be able to run the program, the human-readable code must be compiled into machine code.

**Downloading the Source Code**
-----------------------------

The first thing we need to compile and install source code is the source code itself. For this example, we will be using code from the Internet.

* Open Firefox web browser on your Linux system and browse to `ftp://ftp.bitwizard.nl/mtr`
* Locate the file `mtr-0.86.tar.gz` and click the link to download
* Choose "Save the file" and place it in the Downloads directory

**Extracting the Source Code**
-----------------------------

The source code is zipped-up and compressed into a special archive file known as a Tarball, indicated by the file extension `.tar.gz`. The first thing we must do is extract the files from the Tarball.

* Run the following command to extract the files: `tar xzf mtr-0.86.tar.gz`
* Another long listing shows the extracted files have been placed into a new directory

**Moving into the New Directory**
---------------------------------

Move into the new directory:

`cd ./mtr-0.86`

Inside this directory are all the source code files and a few scripts to help us with the installation.

**Reading the README File**
---------------------------

The first important file that should always come with source code is the README file, which has information about the program and the installation. We should always read this first. If there are any dependencies, they should be listed here as well.

* Open the README file with `less`: `less README`

**Running the Configure Script**
-------------------------------

The configure script creates a makefile that is used by the compiler to compile the source code.

* Run the following command: `sudo ./configure`

**Compiling and Installing the Source Code**
--------------------------------------------

Once the configure script has completed, we can run the "make" command. This command calls the compiler with the makefile and turns all the source code into machine code.

* Run the following command to compile the code: `sudo make`
* We must take the compiled code and install it into the proper directories using the "make" command again.
	+ Run the following command to install the compiled code: `sudo make install`

**Running the Program**
----------------------

If everything has been installed correctly, we can now run the program. The program uses the command "mtr".

* Run the mtr command against your favorite website:
`mtr google.com`