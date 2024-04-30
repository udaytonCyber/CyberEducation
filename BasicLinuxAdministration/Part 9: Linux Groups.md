**Part 9: Linux Groups**
=====================

 Introduction
--------------

In this lab, we'll introduce the concept of groups in Linux and how they can be used to manage access control and permissions.

 What are Groups?
-----------------

* A group is a collection of users that share similar roles or responsibilities.
* Each user can belong to multiple groups.
* Group membership determines which resources (files, directories) a user has access to.

 Managing Groups
----------------

* Create new groups using the `groupadd` command:



bash
￼



sudo groupadd Cincinnati




* Add users to groups using the `usermod` command with the `-a -G` options:



bash
￼



sudo usermod -a -G Cincinnati msmith





 Verifying Group Membership
----------------------------

* View the `/etc/group` file to verify group membership.

 Creating Multiple Groups and Adding Users
---------------------------------------------

Create the following groups and add the indicated members:

1. `Cincinnati`: `msmith`, `tanderson`, `jdenver`, `jfallon`
2. `Managers`: `msmith`, `jfallon`
3. `Developers`: `tanderson`, `jdenver`
4. `Staff`: `msmith`, `tanderson`, `jdenver`, `jfallon`

Note: The `Staff` group is redundant since we have the `Cincinnati` group.

 Deleting a Group
-----------------

* Use the `groupdel` command to delete a group:



bash
￼



sudo groupdel Staff




**Take note of how groups can be used to simplify permission management and access control.**

Note:

1. Groups are stored in the `/etc/group` file.
2. The `groupadd`, `usermod`, and `groupdel` commands are used to manage groups.
3. Users can belong to multiple groups, which determines their access permissions.
4. Group membership is case-sensitive.