**Linux File Types**
=====================

The Linux file system contains several different types of files. It is important to know the difference between them and how to identify them.

**File Extensions vs. Identifiers**
---------------------------------

Unlike other popular operating systems, The command line does not use file extensions such as `.docx`, `.jpg`, `.mp4` etc to identify files. File extensions are used on files in Linux, but they are ignored by the operating system and are generally used to help the user identify the contents of the file.

**File Identifiers**
-------------------

The Linux OS identifies files with a single character that can be found using the `ls -l` command or long listing. The file types and identifiers are as follows:

* `-`: Regular file (simple dash)
	+ A regular file is identified by a simple dash.
	+ Regular files are the most common files found in Linux and can contain data such as text, images, binary program files, audio files etc.
* `d`: Directory
	+ Directories are considered files by the OS which contain pointers to other files.
* `l`: Links (simple link)
	+ Links are files that point to other files or directories. They are similar to a shortcut.
* `c` and `b`: Character and block files
	+ These file types allow programs to communicate with hardware devices on the system.
	+ Block devices are generally storage devices such as hard drives or memory. These are only found in the `/dev` directory.
* `s`: Sockets (simple socket)
	+ Sockets are used for communication between processes.
	+ They are also usually only found in the `/dev` directory.

**Identifying File Types**
-------------------------

We can identify the type of file by the first letter displayed for each file in a long listing (`ls -l`).

### Exercise:
------------

* Run a long directory listing (`ls -l`) for the following directories and try to identify the types of files located in each.
	+ `/`
	+ `/var/log`
	+ `/dev`
    
 **Observations**
-----------------

* The root directory contains mostly other directories. But there are a few links that point to other directories as well.
* In `/var/log` file contains many files with the extension `.log`. These are text regular files that contain text logs from various system processes.
* In `/dev`, you will see character files at the bottom of the listing, but if you scroll up, you will also see block and socket files.