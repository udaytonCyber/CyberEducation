**Linux File System**
=====================

Linux is a file-oriented operating system, which means that many of the administration tasks for managing the OS can be accomplished through the management and editing of files.

### Essential File Management Skills
-----------------------------------

To properly manage a Linux system, you must be familiar with common default directories. While there may be some variation between different kernel versions and distributions, we will cover the most common and often used directories for systems administrators.

**Linux File System Structure**
-----------------------------

The Linux file system is organized in a hierarchical manner, built out from a central point known as the root directory (`/`). From here, directories grow out in branches, separating each directory with a forward slash. You can imagine this like the structure of a tree (Figure 1).

**Common Directories and Their Use**
-----------------------------------

Some common directories found in Linux systems are listed below:

| Directory | Description |
| --- | --- |
| `/` | Root directory containing all other directories discussed above. |
| `etc` | Contains vital information such as configuration files. |
| `var` | Contains log files, among others. |
| `var/log` | Log files for the system. |
| `home/student` | Your home directory for storing files and configurations. |
| `/root` | Root user's home directory (permissions restricted). |

**Directory Listing**
-------------------

To list the contents of each directory:

* Login to Oracle Linux VM as Student with password student.
* Open terminal application.
* Run a directory listing using `ls` command, specifying the directory you want to view.

Note that the root directory (`/`) contains all other directories discussed above. The `/etc` and `/var` directories are important for system administration because they contain vital information such as configuration files and log files respectively.