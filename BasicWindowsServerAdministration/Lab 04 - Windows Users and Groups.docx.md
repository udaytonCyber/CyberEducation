
# Introduction

One of the most important tasks of a systems administrator is controlling who has access to the system and which resources they can use. Often there are many users with different roles in an organization that need access to a computer system but may have different requirements to do their jobs. Using a combination of user accounts, groups, and permissions, we can control at a granular level who has access to certain things on the system. It is important to pay close attention to what a user has access to, as too much access can create security vulnerabilities.

In this lab, we will introduce the basics of creating and managing local users and groups on a Windows system through the graphical user interface.

# Part One: Windows User Accounts

It is likely that you are familiar with using a user account on computer systems. There is a user account on your personal or work laptop, your bank website has one, even to access this lab, you had to use a user account. A user account has two important purposes; to identify a user and authenticate a user.

The identity describes who the user is to a system. This allows the system to know what resources you should be able to access and what actions you can perform. Authentication is the process of proving you are who you say you are. There are many different forms of authentication, but in the case of a local user account, the most common is a combination of the identity (username) and a secret (password).

There are three main types of users accounts in Windows, an **administrator**, a **standard user** account, and a **guest** user. Which type an account is can be determined by if they are a member of the Administrators group, Users group, or Guest group respectively.

When you first install Windows Server, there are two user accounts created. The **Administrator** account, which is a member of the **Administrators group** and the **guest** account, which is disabled by default. Any new user accounts created are automatically added the **Users group** and become standard users, unless manually added the Administrators group.

**There is another type of user account, known as a Power User. This type of account has been deprecated in newer versions of Windows.**

Administrator accounts have complete control over the system. They have permissions to system files and directories, can install software, and make configuration changes to the operating system.

Standard user accounts are only given permissions to their **User directory** and cannot install software of make configuration changes. They may user applications that are made available to all users.

Guest accounts are very limited and cannot make any changes to the system. They may be allowed to run some applications. Guest accounts have very little use outside of a kiosk type of environment and should never be used on a server.

When logging into Windows Server, it requires you to press **Ctrl+Alt+Delete**. When working in a virtual environment, this key combination will not work.

* Look for the **Ctrl+Alt+Delete** button.

![](data:image/png;base64...)

* The only account currently on the system is the Administrator account. Log in with the Password; Pa$$w0rd.

There are a couple different tools we can use to create user accounts. The **Computer Management MMC** is one of the most often used when creating local accounts.

* From the **Server Manager dashboard**, click the **Tools** menu in the top right.
* Select **Computer Management**.

![](data:image/png;base64...)

* Expand the tool, **Local Users and Group**.
* Highlight the **Users** folder.

![](data:image/png;base64...)

In the middle you will see three accounts; **Administrator, DefaultAccount, and Guest**. The DefaultAccount and Guest have a small arrow indicating they are **disabled**. It is suggested you leave these account disabled.

* If you **double click** the Administrator account, it will bring up the **account properties** window. Here you can get information about the account such as; **group membership** and **profile information**.

![](data:image/png;base64...)

* Click the **Member Of** tab.

This shows which groups this user account belongs to. By default, the Administrator account is a member of the Administrators group.

* To create a new account, **right click** on the **Users folder** and select **New User**.

![](data:image/png;base64...)

* Enter in the following information:
  + **User name:** msmith
  + **Full Name:** Mike Smith
  + **Password:** Pa$$w0rd
  + **Confirm Password:** Pa$$w0rd.
  + **Deselect** the “**User must change password at next logon**”
  + Select “**Password never expires**”.
  + Click **Create**.
  + Click **Close**.

![](data:image/png;base64...)

**Having the user change their password when they first login is normally a good idea. That only the user knows the password. Since we are using these accounts for demonstration purposes, we will keep the password we set.**

**Having passwords expire is up for debate these days. For a long time, it was considered a good practice to have passwords expire and force users to create new ones after a period. Some security experts now think this practice has led to users creating weaker passwords and/or writing them down.**

A new user account should appear in the **Users folder**.

![](data:image/png;base64...)

* **Double click** the **msmith account** to open the properties window.
* Switch to the **Members Of** tab.
* Notice that the account was placed into the **Users group** by default.
* Close the properties window.
* Create the following user accounts. Set the password to Pa$$w0rd for each.

| **Full Name** | **User Name** |
| --- | --- |
| Terry Anderson | tanderson |
| Jake Moore | jmoore |
| John Denver | jdenver |
| Jimmy Fallon | jfallon |

* Deleting a user is just as easy.
* **Right click** on the **jmoore** account.
* Select **Delete**.
* Click **Yes** to confirm.

1. **Save a screen shot showing the new user accounts to upload to the Lab Assessment.**

**Windows saves the users passwords in the Security Account Manager (SAM) database file. We are unable to view the contents of this file without special tools, which are outside the scope of this lab.**

# Part Two: Windows Groups

It is possible to manage access control to system resource for each individual user, but with many users on a system, this would be increasingly difficult to manage. Often several users have the same access needs based on their role in the organization. If we organize these users based on their roles, we can make it much easier to manage permissions and access control. We can do this using **groups**. Once we create a group, we can add users to the groups and manage permissions with the groups rather than on an individual basis.

**Windows comes with several predefined groups built in. We have already seen the Administrators and Users groups that determine which type of account a user has. The other built in accounts are designed to give standard users permission to perform certain tasks on the system that would normally be preformed by an Administrator.**

* Click on the **Groups folder** in **Computer Management**.

You can see the list of all of the built-in groups and their description here.

![](data:image/png;base64...)

We will not be using these built in groups, but rather creating new groups to use to apply permissions to files and folders.

* To create a new group, **right click** on the **Groups folder** and select **New Group**.

![](data:image/png;base64...)

* Give the group the name **Cincinnati**.
* Click the **Add** button.
* Enter the username **msmith** in the “**Enter Object names to select**” field.

![](data:image/png;base64...)

* Click **Ok**.

The msmith account should be listed as a member.

* Click **Create**.
* Click **Close**.

The new group should appear at the bottom of the list.

* **Double click** on the new group.

This is the group properties window. The only tab here is the **General tab**. We can add more users here.

* Click the **Add** button.
* Enter the other usernames into the “**Enter the object names to select field**”. Separate each name with a **semi-colon**.

![](data:image/png;base64...)

* Click **Okay**.
* Click **Apply**.
* Click **Ok**.
* Go to the **Users** folder.
* **Double click** the **tanderson** account.
* Switch to the **Member Of** tab.

![](data:image/png;base64...)

You can see that this user is now a member of two groups, **Cincinnati and Users**. We can add additional groups here as well.

* Click the **Add** button.
* Enter the name **Administrators** in the **Enter object names to select field**.
* Click **Ok**.
* Click **Apply**.

![](data:image/png;base64...)

Terry Anderson is now part of the Administrators group, giving him administrative privileges to the system.

Create the following groups and give the users specified membership to each.

| Group Name | Users |
| --- | --- |
| ***Cincinnati*** | ***msmith, tanderson, jdenver, jfallon*** |
| ***Managers*** | ***msmith, jfallon*** |
| ***Developers*** | ***tanderson, jdenver*** |
| ***Staff*** | ***msmith, tanderson, jdenver, jfallon*** |

1. **Save a screen shot showing the new groups to upload for the lab assessment.**


# Introduction

One of the most important tasks of a systems administrator is controlling who has access to the system and which resources they can use. Often there are many users with different roles in an organization that need access to a computer system but may have different requirements to do their jobs. Using a combination of user accounts, groups, and permissions, we can control at a granular level who has access to certain things on the system. It is important to pay close attention to what a user has access to, as too much access can create security vulnerabilities.

In this lab, we will introduce the basics of creating and managing local users and groups on a Windows system through the graphical user interface.

# Part One: Windows User Accounts

It is likely that you are familiar with using a user account on computer systems. There is a user account on your personal or work laptop, your bank website has one, even to access this lab, you had to use a user account. A user account has two important purposes; to identify a user and authenticate a user.

The identity describes who the user is to a system. This allows the system to know what resources you should be able to access and what actions you can perform. Authentication is the process of proving you are who you say you are. There are many different forms of authentication, but in the case of a local user account, the most common is a combination of the identity (username) and a secret (password).

There are three main types of users accounts in Windows, an **administrator**, a **standard user** account, and a **guest** user. Which type an account is can be determined by if they are a member of the Administrators group, Users group, or Guest group respectively.

When you first install Windows Server, there are two user accounts created. The **Administrator** account, which is a member of the **Administrators group** and the **guest** account, which is disabled by default. Any new user accounts created are automatically added the **Users group** and become standard users, unless manually added the Administrators group.

**There is another type of user account, known as a Power User. This type of account has been deprecated in newer versions of Windows.**

Administrator accounts have complete control over the system. They have permissions to system files and directories, can install software, and make configuration changes to the operating system.

Standard user accounts are only given permissions to their **User directory** and cannot install software of make configuration changes. They may user applications that are made available to all users.

Guest accounts are very limited and cannot make any changes to the system. They may be allowed to run some applications. Guest accounts have very little use outside of a kiosk type of environment and should never be used on a server.

When logging into Windows Server, it requires you to press **Ctrl+Alt+Delete**. When working in a virtual environment, this key combination will not work.

* Look for the **Ctrl+Alt+Delete** button.

![](data:image/png;base64...)

* The only account currently on the system is the Administrator account. Log in with the Password; Pa$$w0rd.

There are a couple different tools we can use to create user accounts. The **Computer Management MMC** is one of the most often used when creating local accounts.

* From the **Server Manager dashboard**, click the **Tools** menu in the top right.
* Select **Computer Management**.

![](data:image/png;base64...)

* Expand the tool, **Local Users and Group**.
* Highlight the **Users** folder.

![](data:image/png;base64...)

In the middle you will see three accounts; **Administrator, DefaultAccount, and Guest**. The DefaultAccount and Guest have a small arrow indicating they are **disabled**. It is suggested you leave these account disabled.

* If you **double click** the Administrator account, it will bring up the **account properties** window. Here you can get information about the account such as; **group membership** and **profile information**.

![](data:image/png;base64...)

* Click the **Member Of** tab.

This shows which groups this user account belongs to. By default, the Administrator account is a member of the Administrators group.

* To create a new account, **right click** on the **Users folder** and select **New User**.

![](data:image/png;base64...)

* Enter in the following information:
  + **User name:** msmith
  + **Full Name:** Mike Smith
  + **Password:** Pa$$w0rd
  + **Confirm Password:** Pa$$w0rd.
  + **Deselect** the “**User must change password at next logon**”
  + Select “**Password never expires**”.
  + Click **Create**.
  + Click **Close**.

![](data:image/png;base64...)

**Having the user change their password when they first login is normally a good idea. That only the user knows the password. Since we are using these accounts for demonstration purposes, we will keep the password we set.**

**Having passwords expire is up for debate these days. For a long time, it was considered a good practice to have passwords expire and force users to create new ones after a period. Some security experts now think this practice has led to users creating weaker passwords and/or writing them down.**

A new user account should appear in the **Users folder**.

![](data:image/png;base64...)

* **Double click** the **msmith account** to open the properties window.
* Switch to the **Members Of** tab.
* Notice that the account was placed into the **Users group** by default.
* Close the properties window.
* Create the following user accounts. Set the password to Pa$$w0rd for each.

| **Full Name** | **User Name** |
| --- | --- |
| Terry Anderson | tanderson |
| Jake Moore | jmoore |
| John Denver | jdenver |
| Jimmy Fallon | jfallon |

* Deleting a user is just as easy.
* **Right click** on the **jmoore** account.
* Select **Delete**.
* Click **Yes** to confirm.

1. **Save a screen shot showing the new user accounts to upload to the Lab Assessment.**

**Windows saves the users passwords in the Security Account Manager (SAM) database file. We are unable to view the contents of this file without special tools, which are outside the scope of this lab.**

# Part Two: Windows Groups

It is possible to manage access control to system resource for each individual user, but with many users on a system, this would be increasingly difficult to manage. Often several users have the same access needs based on their role in the organization. If we organize these users based on their roles, we can make it much easier to manage permissions and access control. We can do this using **groups**. Once we create a group, we can add users to the groups and manage permissions with the groups rather than on an individual basis.

**Windows comes with several predefined groups built in. We have already seen the Administrators and Users groups that determine which type of account a user has. The other built in accounts are designed to give standard users permission to perform certain tasks on the system that would normally be preformed by an Administrator.**

* Click on the **Groups folder** in **Computer Management**.

You can see the list of all of the built-in groups and their description here.

![](data:image/png;base64...)

We will not be using these built in groups, but rather creating new groups to use to apply permissions to files and folders.

* To create a new group, **right click** on the **Groups folder** and select **New Group**.

![](data:image/png;base64...)

* Give the group the name **Cincinnati**.
* Click the **Add** button.
* Enter the username **msmith** in the “**Enter Object names to select**” field.

![](data:image/png;base64...)

* Click **Ok**.

The msmith account should be listed as a member.

* Click **Create**.
* Click **Close**.

The new group should appear at the bottom of the list.

* **Double click** on the new group.

This is the group properties window. The only tab here is the **General tab**. We can add more users here.

* Click the **Add** button.
* Enter the other usernames into the “**Enter the object names to select field**”. Separate each name with a **semi-colon**.

![](data:image/png;base64...)

* Click **Okay**.
* Click **Apply**.
* Click **Ok**.
* Go to the **Users** folder.
* **Double click** the **tanderson** account.
* Switch to the **Member Of** tab.

![](data:image/png;base64...)

You can see that this user is now a member of two groups, **Cincinnati and Users**. We can add additional groups here as well.

* Click the **Add** button.
* Enter the name **Administrators** in the **Enter object names to select field**.
* Click **Ok**.
* Click **Apply**.

![](data:image/png;base64...)

Terry Anderson is now part of the Administrators group, giving him administrative privileges to the system.

Create the following groups and give the users specified membership to each.

| Group Name | Users |
| --- | --- |
| ***Cincinnati*** | ***msmith, tanderson, jdenver, jfallon*** |
| ***Managers*** | ***msmith, jfallon*** |
| ***Developers*** | ***tanderson, jdenver*** |
| ***Staff*** | ***msmith, tanderson, jdenver, jfallon*** |

1. **Save a screen shot showing the new groups to upload for the lab assessment.**

