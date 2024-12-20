
# Introduction

With some basic Windows system administration skills, we can set up and configure a server to provide file sharing and web services to the network. In this lab we will configure two Server Roles, **File and Storage Services** and **Internet Information Services (IIS).** We will also learn about Windows file permissions.

# Part Zero: Pre-Lab Requirements

If you have not completed the previous labs in this sequence, you will need to setup a few things before you get started:

Log into the system as administrator with the password Pa$$w0rd.

Create the following user accounts and set the password to Pa$$w0rd for each:

| **Full Name** | **User Name** |
| --- | --- |
| Terry Anderson | tanderson |
| Mike Smith | smith |
| John Denver | jdenver |
| Jimmy Fallon | jfallon |

Add the users to their appropriate groups:

| Group Name | Users |
| --- | --- |
| ***Cincinnati*** | ***msmith, tanderson, jdenver, jfallon*** |
| ***Managers*** | ***msmith, jfallon*** |
| ***Developers*** | ***tanderson, jdenver*** |

# Part One: File and Storage Services

When you first install Windows Server 2016, the **File and Storage Services** role is installed by default. It is not however configured to work as a shared file server out of the box. We will have to install a couple of **Role Services** and **Features** to get it ready. Luckily, we can do all of this through **Wizards**.

* In the **Server Manager**, select **Add and Roles and Features** from the **Manage** menu.

![](data:image/png;base64...)

* Click **Next** until you get to the **Select Server Roles** screen.
* Expand **File and Storage Services**.
* Expand **File and iSCSI Services.**
* Select the **File Server** role.

![](data:image/png;base64...)

* Click **Next.**
* Click **Next** again, then click **Install.**
* Once the installation is complete, click on the **File and Storage Services** role on the left-hand side of **Server Manager**.

![](data:image/png;base64...)

* From inside the **File and Storage Services** window, click on **Shares** on the left-hand side.

![](data:image/png;base64...)

Here you can see there is a link to start the **New Share Wizard**.

* Click the link to begin the Wizard.

First, we must select the type of network share we want to create. We have the choice between **SMB (Server message block)** and **NFS (Network File System)**. As you can see in the description, SMB is typically used for shared files with Windows-based computers.

* Select **SMB Share – Quick.**

![](data:image/png;base64...)

* Click **Next.**
* Next, we need to select the **Share Location**. This is the server and volume that we want to create the shared folder. We only have one option for each.

![](data:image/png;base64...)

Click **Next.**

The **Share name** should describe what will be stored in the folder or who will have access to it. For our example, we will name them after the groups we have previously created.

* Enter **Cincinnat**i for the **Share name.**
* Take note of the **local path** and the **remote path** for the share. The local path is where the folder will be created on the server. The remote path is the **UNC path** that we will use to connect to the share from another computer.

![](data:image/png;base64...)

Click **Next.**

* We can set up other settings, such as **Encrypted data access**, but for now leave the defaults and click **next.**

The next screen displays the default permissions and gives us the opportunity to customize the permissions. For now, we will leave the defaults in place. We will change them in the next section.

![](data:image/png;base64...)

* Click **Next.**

The next page is the confirmation page.

* Click **Create** to finish the Wizard.
* You will see a new share has been created. To create another share, **right click** beneath the current one and select **New Share.**
* Go ahead and create two more shares, one for the **Developers** group and one for the **Managers** group.

1. **Save a screen shot showing all three shares within Server Manager for the lab assessment.**

# Part Two: Windows File Permissions

Windows file permission tend to be a little complex. The good thing about them being complex is that you can fine tune your permissions. The downside is sometimes they can become difficult to manage.

Windows File Services has two sets of permissions. The first set of permissions is known as the **NTFS file permissions.** These permissions apply when accessing the file or folders **locally and over the network.** The second set of permissions is known as the **Share permissions**. These permissions only apply when accessing a file or folder over the network.

With NTFS permissions, we have **six basic permissions** and then several more granular **advanced permissions**. For this lesson, we will only focus on the six basic permissions. Those permissions include:

* **Read** - Permits viewing or accessing of the file
* **Write** - Permits adding to a folder or writing to a file
* **Read & Execute** - Permits viewing and accessing files as well as executing of a file
* **List Folder Contents** - Permits viewing and listing of files and subfolders as well as executing of files - Applies only to Folders
* **Modify** - Permits reading and writing of the file; also allow deletion of the file
* **Full Control** - Permits reading, writing, changing permissions, and deleting files

**Along with allow each of the above permissions, you can also Deny a permission to a user or group. It is not advised to get into the habit of using Deny permissions unless it is special circumstance. For instance, an employee was just let go from the company and you want to ensure all his permissions to files was revoked.**

By default, the following NTFS permissions are set for users and groups:

* **Administrators** – Full control
* **Users** – Read and execute
* **Creator/Owner** – Full control

**NTFS permissions when set to a folder, apply to all sub folders and files. This is known as inheritance. This can be disabled, but that’s for a more advanced lesson.**

**Share permissions** in windows are a little simpler. They apply only when the file or folder is accessed over the network through file sharing. The share permissions that can be set are as follows:

* **Read** – Permits viewing and accessing a file or folder.
* **Change** – Permits users to read, create, edit, or delete a file or folder
* **Full Control** – Permits users to read, create, edit, delete, or change permissions on a file or folder.

The default share permission is set to give the **Everyone group** read permissions to the Share. These permissions will need to be modified to allow anyone to edit files.

**The Everyone group is a special group that automatically includes all Windows users. You cannot add or remove members from this group manually.**

Since permissions can be set at different levels, there is always the possibility two permission may conflict with each other. There are five rules that are applied when two permission conflict to determine which permission is applied. They are as follows:

1. **Least restrictive (most permissive) explicit permission win**
2. **Deny permissions take precedence over allow**
3. **Permissions are cumulative**
4. **Permissions applied directly to an object take precedence over permissions inherited from a parent**
5. **When connecting over a network, most restrictive permission between Share and NTFS permission take precedence**

Now let’s setup permissions so that the appropriate groups can access the correct files.

* In **Server Manager**, right click the **Cincinnati** share and choose **properties.**
* Click on the **Permissions tab** on the left-hand side.
* Click on the **Customize permissions** button.

![](data:image/png;base64...)

The first tab labeled **permissions** is for the **NTFS permissions**. The default permissions are already set.

![](data:image/png;base64...)

We need to set the permissions for the **Cincinnati group** to give them the ability to edit and create files. To do this, we will set the **Modify** permission for this group.

**Generally, you do not want to give regular users Full Control. Allowing users to change permissions could lead to someone being able to access something they are not supposed to have. You could lose control of the management of permissions very quickly.**

* Click the **Add** button.

![](data:image/png;base64...)

* Click **select a principal** to select the group.
* Enter the group name **Cincinnati.**
* Click **Ok.**
* Select the **Modify** permission.

![](data:image/png;base64...)

**Notice that all other permissions are selected. Permission are cumulative, so if a lessor permission is part of the highest selected permission, then it will also be selected.**

* Click **Ok.**
* Click **Apply**.

**When setting permission, you must never use the “X” to close the window. If you do not hit Apply, then OK, the permissions will not be changed.**

* Click on the **Share** tab.

![](data:image/png;base64...)

Because of **conflict rule #5**, the most restrictive permission between Share and NTFS permissions wins. Currently the most restrictive permissions for any one in the Cincinnati group would be the Share permissions of everyone having only read. These means no one would be able to edit files.

Therefore, we must give the Cincinnati group Change permissions on the Share side.

* Click **Add.**
* Click **select a principal.**
* Enter the group name **Cincinnati.**
* Click **Ok.**
* Select **Change.**

![](data:image/png;base64...)

* Click **Okay.**
* Click **Apply.**

Now that we have set the permissions. We can use the **Effective Access** tab to verify the permissions are set correctly.

* Click the **Effective Access** tab.
* Click **Select a User**.
* Enter the group name **Cincinnati.**
* Click **Ok.**
* Click the **View effective access** button.

![](data:image/png;base64...)

This display shows use what users of the Cincinnati group can and cannot do within the Cincinnati Folder. It also shows us on the right, what permission level is limiting the access.

* Click **OK** to close the **Security Settings** window.
* Then **Click Apply** and **Ok** on the **Cincinnati properties** windows to apply the changes we have made.
* Go through and setup the permissions for the **Managers** and **Developers** shares so that those groups have modify permissions to those shares as well.
* Run the **Effective access** tool for each group on their corresponding shares.

1. **Save a screen shot of the Effective access tool for the Managers group on the managers share for the lab assessment.**
2. **Save a screen shot of the Effective access tool for the Developers group on the Developers share for the lab assessment.**

# Part Three: Accessing Windows Share from a Windows Client

If everything is configured correctly, we should be able to now connect to the Windows shares over the network with **Windows File Explorer**.

* Log into your Windows 10 system
* Open **Windows File Explorer** (the folder Icon) ![](data:image/png;base64...)
* In the address bar, enter the **UNC path** \\<servername> **replacing <servername>** with your Windows server computer name.

![](data:image/png;base64...)

Click **Ente**r.

* You will be prompted for a username and password.
* Login with the **tanderson** account.

You should see three network folders.

![](data:image/png;base64...)

1. **Open each folder and attempt to make a new file or folder. Take note of which folders work and which folders do not for the Lab Assessment.**

# Part four: Internet Information Services (IIS Web Server)

* While on your **Windows 10** system, open a web browser and download the website files (if you don’t already have them saved. <https://uc.box.com/v/SystemAdminWebSite>
* Download the **Website zip** file to your **Desktop**.
* **Right click** the file and choose **extract all**.
* Click the button to **extract** the files.
* Open the **Index.html** file with **notepad.**
* Edit the following lines replacing the stand in text with your name:

<title>Your Name here</title>

<h1>UserName’s Test HTML Page</h1>

* **Save and close** the file.
* Copy the **Index.html** file and **images folder** to the **Developers** share.

Now we have put the website files in place, go back to your Windows Server and we will setup IIS to server this website over the network.

* Begin the **Add Roles and Features** Wizard.
* This time select the **Web Server (IIS)** Role.
* Click **Add Features** to install the **IIS Management Console**.
* Complete the Wizard accepting the **default** selections.
* Once the install is complete. Go to **Tools** menu in **Server Manager**.
* Select the new tool, **Internet Information Services (IIS) Manger.**

This is a tool that will allow us to change configuration settings for our web server.

* From the left-hand side, under **Connections**.
* Expand the **server icon**.
* Expand the **Sites folder.**
* Click on **Default Web Site.**

![](data:image/png;base64...)

On the right-side of the **IIS Manger** tool, click the link for **Basic Settings**.

![](data:image/png;base64...)

* Click the ellipses **(…)** button for the **Physical Path.**

![](data:image/png;base64...)

* Browser to the directory **C:/Shares/Developers.**
* Click **Ok.**
* Click **Ok** on the **Edit Site** window.
* Go back to your **Windows 10** client and open a web browser.
* Enter http://<servername> into the address bar. (Replacing <servername> with your Windows server computers name.)

1. **Save a screen shot of the displayed website for the lab assessment.**


# Introduction

With some basic Windows system administration skills, we can set up and configure a server to provide file sharing and web services to the network. In this lab we will configure two Server Roles, **File and Storage Services** and **Internet Information Services (IIS).** We will also learn about Windows file permissions.

# Part Zero: Pre-Lab Requirements

If you have not completed the previous labs in this sequence, you will need to setup a few things before you get started:

Log into the system as administrator with the password Pa$$w0rd.

Create the following user accounts and set the password to Pa$$w0rd for each:

| **Full Name** | **User Name** |
| --- | --- |
| Terry Anderson | tanderson |
| Mike Smith | smith |
| John Denver | jdenver |
| Jimmy Fallon | jfallon |

Add the users to their appropriate groups:

| Group Name | Users |
| --- | --- |
| ***Cincinnati*** | ***msmith, tanderson, jdenver, jfallon*** |
| ***Managers*** | ***msmith, jfallon*** |
| ***Developers*** | ***tanderson, jdenver*** |

# Part One: File and Storage Services

When you first install Windows Server 2016, the **File and Storage Services** role is installed by default. It is not however configured to work as a shared file server out of the box. We will have to install a couple of **Role Services** and **Features** to get it ready. Luckily, we can do all of this through **Wizards**.

* In the **Server Manager**, select **Add and Roles and Features** from the **Manage** menu.

![](data:image/png;base64...)

* Click **Next** until you get to the **Select Server Roles** screen.
* Expand **File and Storage Services**.
* Expand **File and iSCSI Services.**
* Select the **File Server** role.

![](data:image/png;base64...)

* Click **Next.**
* Click **Next** again, then click **Install.**
* Once the installation is complete, click on the **File and Storage Services** role on the left-hand side of **Server Manager**.

![](data:image/png;base64...)

* From inside the **File and Storage Services** window, click on **Shares** on the left-hand side.

![](data:image/png;base64...)

Here you can see there is a link to start the **New Share Wizard**.

* Click the link to begin the Wizard.

First, we must select the type of network share we want to create. We have the choice between **SMB (Server message block)** and **NFS (Network File System)**. As you can see in the description, SMB is typically used for shared files with Windows-based computers.

* Select **SMB Share – Quick.**

![](data:image/png;base64...)

* Click **Next.**
* Next, we need to select the **Share Location**. This is the server and volume that we want to create the shared folder. We only have one option for each.

![](data:image/png;base64...)

Click **Next.**

The **Share name** should describe what will be stored in the folder or who will have access to it. For our example, we will name them after the groups we have previously created.

* Enter **Cincinnat**i for the **Share name.**
* Take note of the **local path** and the **remote path** for the share. The local path is where the folder will be created on the server. The remote path is the **UNC path** that we will use to connect to the share from another computer.

![](data:image/png;base64...)

Click **Next.**

* We can set up other settings, such as **Encrypted data access**, but for now leave the defaults and click **next.**

The next screen displays the default permissions and gives us the opportunity to customize the permissions. For now, we will leave the defaults in place. We will change them in the next section.

![](data:image/png;base64...)

* Click **Next.**

The next page is the confirmation page.

* Click **Create** to finish the Wizard.
* You will see a new share has been created. To create another share, **right click** beneath the current one and select **New Share.**
* Go ahead and create two more shares, one for the **Developers** group and one for the **Managers** group.

1. **Save a screen shot showing all three shares within Server Manager for the lab assessment.**

# Part Two: Windows File Permissions

Windows file permission tend to be a little complex. The good thing about them being complex is that you can fine tune your permissions. The downside is sometimes they can become difficult to manage.

Windows File Services has two sets of permissions. The first set of permissions is known as the **NTFS file permissions.** These permissions apply when accessing the file or folders **locally and over the network.** The second set of permissions is known as the **Share permissions**. These permissions only apply when accessing a file or folder over the network.

With NTFS permissions, we have **six basic permissions** and then several more granular **advanced permissions**. For this lesson, we will only focus on the six basic permissions. Those permissions include:

* **Read** - Permits viewing or accessing of the file
* **Write** - Permits adding to a folder or writing to a file
* **Read & Execute** - Permits viewing and accessing files as well as executing of a file
* **List Folder Contents** - Permits viewing and listing of files and subfolders as well as executing of files - Applies only to Folders
* **Modify** - Permits reading and writing of the file; also allow deletion of the file
* **Full Control** - Permits reading, writing, changing permissions, and deleting files

**Along with allow each of the above permissions, you can also Deny a permission to a user or group. It is not advised to get into the habit of using Deny permissions unless it is special circumstance. For instance, an employee was just let go from the company and you want to ensure all his permissions to files was revoked.**

By default, the following NTFS permissions are set for users and groups:

* **Administrators** – Full control
* **Users** – Read and execute
* **Creator/Owner** – Full control

**NTFS permissions when set to a folder, apply to all sub folders and files. This is known as inheritance. This can be disabled, but that’s for a more advanced lesson.**

**Share permissions** in windows are a little simpler. They apply only when the file or folder is accessed over the network through file sharing. The share permissions that can be set are as follows:

* **Read** – Permits viewing and accessing a file or folder.
* **Change** – Permits users to read, create, edit, or delete a file or folder
* **Full Control** – Permits users to read, create, edit, delete, or change permissions on a file or folder.

The default share permission is set to give the **Everyone group** read permissions to the Share. These permissions will need to be modified to allow anyone to edit files.

**The Everyone group is a special group that automatically includes all Windows users. You cannot add or remove members from this group manually.**

Since permissions can be set at different levels, there is always the possibility two permission may conflict with each other. There are five rules that are applied when two permission conflict to determine which permission is applied. They are as follows:

1. **Least restrictive (most permissive) explicit permission win**
2. **Deny permissions take precedence over allow**
3. **Permissions are cumulative**
4. **Permissions applied directly to an object take precedence over permissions inherited from a parent**
5. **When connecting over a network, most restrictive permission between Share and NTFS permission take precedence**

Now let’s setup permissions so that the appropriate groups can access the correct files.

* In **Server Manager**, right click the **Cincinnati** share and choose **properties.**
* Click on the **Permissions tab** on the left-hand side.
* Click on the **Customize permissions** button.

![](data:image/png;base64...)

The first tab labeled **permissions** is for the **NTFS permissions**. The default permissions are already set.

![](data:image/png;base64...)

We need to set the permissions for the **Cincinnati group** to give them the ability to edit and create files. To do this, we will set the **Modify** permission for this group.

**Generally, you do not want to give regular users Full Control. Allowing users to change permissions could lead to someone being able to access something they are not supposed to have. You could lose control of the management of permissions very quickly.**

* Click the **Add** button.

![](data:image/png;base64...)

* Click **select a principal** to select the group.
* Enter the group name **Cincinnati.**
* Click **Ok.**
* Select the **Modify** permission.

![](data:image/png;base64...)

**Notice that all other permissions are selected. Permission are cumulative, so if a lessor permission is part of the highest selected permission, then it will also be selected.**

* Click **Ok.**
* Click **Apply**.

**When setting permission, you must never use the “X” to close the window. If you do not hit Apply, then OK, the permissions will not be changed.**

* Click on the **Share** tab.

![](data:image/png;base64...)

Because of **conflict rule #5**, the most restrictive permission between Share and NTFS permissions wins. Currently the most restrictive permissions for any one in the Cincinnati group would be the Share permissions of everyone having only read. These means no one would be able to edit files.

Therefore, we must give the Cincinnati group Change permissions on the Share side.

* Click **Add.**
* Click **select a principal.**
* Enter the group name **Cincinnati.**
* Click **Ok.**
* Select **Change.**

![](data:image/png;base64...)

* Click **Okay.**
* Click **Apply.**

Now that we have set the permissions. We can use the **Effective Access** tab to verify the permissions are set correctly.

* Click the **Effective Access** tab.
* Click **Select a User**.
* Enter the group name **Cincinnati.**
* Click **Ok.**
* Click the **View effective access** button.

![](data:image/png;base64...)

This display shows use what users of the Cincinnati group can and cannot do within the Cincinnati Folder. It also shows us on the right, what permission level is limiting the access.

* Click **OK** to close the **Security Settings** window.
* Then **Click Apply** and **Ok** on the **Cincinnati properties** windows to apply the changes we have made.
* Go through and setup the permissions for the **Managers** and **Developers** shares so that those groups have modify permissions to those shares as well.
* Run the **Effective access** tool for each group on their corresponding shares.

1. **Save a screen shot of the Effective access tool for the Managers group on the managers share for the lab assessment.**
2. **Save a screen shot of the Effective access tool for the Developers group on the Developers share for the lab assessment.**

# Part Three: Accessing Windows Share from a Windows Client

If everything is configured correctly, we should be able to now connect to the Windows shares over the network with **Windows File Explorer**.

* Log into your Windows 10 system
* Open **Windows File Explorer** (the folder Icon) ![](data:image/png;base64...)
* In the address bar, enter the **UNC path** \\<servername> **replacing <servername>** with your Windows server computer name.

![](data:image/png;base64...)

Click **Ente**r.

* You will be prompted for a username and password.
* Login with the **tanderson** account.

You should see three network folders.

![](data:image/png;base64...)

1. **Open each folder and attempt to make a new file or folder. Take note of which folders work and which folders do not for the Lab Assessment.**

# Part four: Internet Information Services (IIS Web Server)

* While on your **Windows 10** system, open a web browser and download the website files (if you don’t already have them saved. <https://uc.box.com/v/SystemAdminWebSite>
* Download the **Website zip** file to your **Desktop**.
* **Right click** the file and choose **extract all**.
* Click the button to **extract** the files.
* Open the **Index.html** file with **notepad.**
* Edit the following lines replacing the stand in text with your name:

<title>Your Name here</title>

<h1>UserName’s Test HTML Page</h1>

* **Save and close** the file.
* Copy the **Index.html** file and **images folder** to the **Developers** share.

Now we have put the website files in place, go back to your Windows Server and we will setup IIS to server this website over the network.

* Begin the **Add Roles and Features** Wizard.
* This time select the **Web Server (IIS)** Role.
* Click **Add Features** to install the **IIS Management Console**.
* Complete the Wizard accepting the **default** selections.
* Once the install is complete. Go to **Tools** menu in **Server Manager**.
* Select the new tool, **Internet Information Services (IIS) Manger.**

This is a tool that will allow us to change configuration settings for our web server.

* From the left-hand side, under **Connections**.
* Expand the **server icon**.
* Expand the **Sites folder.**
* Click on **Default Web Site.**

![](data:image/png;base64...)

On the right-side of the **IIS Manger** tool, click the link for **Basic Settings**.

![](data:image/png;base64...)

* Click the ellipses **(…)** button for the **Physical Path.**

![](data:image/png;base64...)

* Browser to the directory **C:/Shares/Developers.**
* Click **Ok.**
* Click **Ok** on the **Edit Site** window.
* Go back to your **Windows 10** client and open a web browser.
* Enter http://<servername> into the address bar. (Replacing <servername> with your Windows server computers name.)

1. **Save a screen shot of the displayed website for the lab assessment.**

