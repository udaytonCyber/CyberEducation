**Part 8: Linux Users**
=====================

### Introduction
--------------

In this lab, we'll introduce the basics of creating and managing local users, groups, and permissions on a Linux system through the command line interface.

 User Accounts
-------------

* A user accounts have two important purposes:
	+ Identify a user (username)
	+ Authenticate a user (password)

Linux has two types of user accounts:

1. Superuser account (`root`): created by default, with complete access to everything on the system.
2. Normal accounts: limited to running certain applications and accessing only files and directories they have permission to access.

Normal accounts can be given the ability to run as a superuser using the `sudo` command (super user do).

 Creating Users
--------------

* Use the `useradd` command to create new users:



bash
￼



sudo useradd -c "Mike Smith" msmith




The `-c` option allows us to add the full name in the comment field.

 Verifying User Accounts
----------------------

* View the `/etc/passwd` file to verify the new account was added.
* Set a password for the user:



bash
￼



sudo passwd msmith





 Creating Additional Users
-------------------------

Create the following users and set their passwords:

1. Terry Anderson (`tanderson`)
2. Jake Moore (`jmoore`)
3. John Denver (`jdenver`)
4. Jimmy Fallon (`jfallon`)

Deleting User Accounts
---------------------

* Use the `userdel` command to remove user accounts:



bash
￼



sudo userdel -r jmoore




The `-r` option removes the user's home directory.

 Switching Users with `su`
----------------------------

* Use the `su` command to switch users and test permissions:



bash
￼



su msmith





 Going Back to Original User Account
-----------------------------------

* Exit the new user account: `exit`

 Using `sudo`
-------------

* Run a command as root using `sudo`: `sudo <command>`
* Add other users to the `sudoers` file using `visudo`.

**Take a screenshot of the end `/etc/passwd` file showing the new users for the Lab Assessment.**

Note:

1. The `useradd`, `passwd`, and `userdel` commands are used to manage user accounts.
2. The `su` command is used to switch between user accounts, while `sudo` allows running a command as root.
3. The `/etc/passwd` file contains information about all users on the system.
4. The `/etc/shadow` file stores passwords in hashed form for security reasons.