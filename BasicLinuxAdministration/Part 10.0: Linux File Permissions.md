**Part 10: Linux File Permissions**
=====================================

 Introduction
--------------

In this lab, we'll explore how to manage file permissions on a Linux system using the `chmod`, `chown`, and `chgrp` commands.

 Understanding File Permissions
-------------------------------

* Each file or directory has three levels of permission:
	+ Owner (u): The user who owns the file.
	+ Group (g): A group of users that can access the file.
	+ Other (o): Everyone else on the system.
* Each level has three permissions: Read (r), Write (w), and Execute (x).
* Permissions are represented as a 3-digit number, with each digit representing the owner, group, or other permission.

 Changing File Permissions
---------------------------

* Use `chmod` to change file permissions:



bash
￼



sudo chmod <permissions> /path/to/file




Example: Set the Cincinnati directory's permissions to rwx for the group and everyone else.



bash
￼



sudo chgrp Cincinnati /share/Cincinnati
sudo chmod 775 /share/Cincinnati





 Changing File Ownership
-------------------------

* Use `chown` to change file ownership:



bash
￼



sudo chown <owner> /path/to/file




Example: Set the owner of the Cincinnati directory to Mike Smith.



bash
￼



sudo chown msmith /share/Cincinnati





 Testing Permissions
-------------------

* Test permissions by creating files in each directory using `touch` command.

**Take note of how file permissions can be used to control access and restrict changes to sensitive data.**

Note:

1. The `chmod`, `chown`, and `chgrp` commands are used to manage file permissions, ownership, and group membership.
2. Each level (owner, group, other) has three permissions: Read, Write, and Execute.
3. Permissions can be represented as a 3-digit number or using the rwx notation.
4. File permissions should be set according to least privilege principle, granting access only to what is necessary for each user's role.