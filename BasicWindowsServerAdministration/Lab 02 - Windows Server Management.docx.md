
# Introduction

Installing an operating system is just the first step. What we have now is often referred to as a “vanilla” OS, which means we have a default installation. However, each system we setup is going to have different needs and configurations. Before we can start configuring the server, we need to learn about the tools we can use.

In this lab you will explore the many tools that Windows provides with the operating system to control and configure the system to our needs. Microsoft does a pretty good job at developing GUI based tools for most tasks, so for now we will focus on those.

# Part 1: Basic Navigation

Log into the **Windows Server** as **Administrator**

**When we first log into Windows Server, the Server Manager application automatically starts up. This is a useful tool that we will learn about later, but you can close the window for now.**

If you are a Windows 10 user, the screen show below should look familiar. This is known as the Desktop and is a user workspace. On the main part of the desktop, windows for programs that have GUI interfaces will appear. You can also save shortcuts to commonly used programs on the Desktop for easy access. On the bottom of the screen, highlighted in red, is the task bar. Here you will find several useful tools:

* Circled in orange is the Start Menu. Here you can find a list of all applications installed on the system.
* Circled in yellow is the search icon. You can quickly search for applications, files, or even the web from here.
* Circled in blue is Internet Explorer. This is an application that allow you to browse the internet. It’s not a good idea to browse the internet from a server and this version of Internet Explorer has a lot of security turned on.
* Circled in green is the Windows File Explorer. This application allows you to browse folders, files, and disks attached to your system. We will look at this in more depth in Lab 3.
* Circled in purple is the Notification Tray. Here you will find helpful information, such as alerts and programs that run in the background.

![](data:image/jpeg;base64...)

* Click the **Start Menu** icon.

The Start Menu has three distinct areas:

* In red, you will find icons that allow you:
  + Sign-out or switch users
  + Quickly access the settings
  + Power off or restart the system
* In green is the all programs list. This is an alphabetical list of all applications and tools installed on the system.
* In blue is the quick access tiles. There are commonly used programs. You can customize what shows up here.

![](data:image/png;base64...)

* Click the **Action Center icon** on the far right of the task bar.

In the Action Center, you will see alerts for your system and be able to quickly access network and other settings. You can see that my system currently needs some updates.

![](data:image/png;base64...)

* Right click on the **task bar**.

This will bring up another hidden menu that has option that allow you to control the task bar and other settings. A very useful tool that can be found here is the Task Manager. This allows you to monitor and control services on the system.

![](data:image/png;base64...)

* Click on the **search icon**.
* Type in **Server Manager** in the search bar.

The search feature in Windows Server will quickly let you find applications and files.

* Click on the **Server Manager Desktop app** to open that tool again.

![](data:image/png;base64...)

# Part 2: Server Manager

The Server Manager tool is a very useful application that provides a central location to view information about our server and have quick access to many commonly used tools for administering our server roles and features. We can even use this tool to view and manage other Windows Servers on the network.

![](data:image/png;base64...)

On the left-hand side of the Server Manager, we have several different tabs:

**Dashboard** – This is a quick start view with some common task we can run and an overview of the status of our server and server roles. As you can see, there are some red alerts on the example system.

* Click on the **Local Server** tab.

**Local Server** – This is where we can view information about our server and quickly access tools for changing configurations as we saw in Lab 1.

* Scroll down on the Local Server window.

As we scroll down, we can see more information:

**Events** – This are log event log entries related to our system. These can be error messages, warnings, or just informational. This is a great place to start troubleshooting.

**Services** – This is a list of all the services installed on our system. We can quickly check the status, start, or stop services from here.

![](data:image/png;base64...)

* Scroll down further.

**Best Practices Analyzer and Performance** – There is no information here currently, but we could turn on some performance monitoring tools to gather information about how our system is running.

* Scroll to the bottom.

**Roles and Features** – Here we will see information about all the roles and features currently installed on our server.

![](data:image/png;base64...)

**The All Servers tab is like the local server tab. The difference is it will allow viewing of information and control over other servers on the network if we set them up. For now, we are only looking into a single server.**

* Click on the **File and Storage Services** tab.

![](data:image/png;base64...)

This tab is for a Server Role called File and Storage Services that is installed by default on our system. Here we can manage volumes, disks, and storage pools. In later labs we will use this tool to also manage file shares.

**As we install more Server Roles on to our server, more tabs will appear. Each tab will give use access to tools and information necessary to mange them.**

In the **top right corner** of the **Server Manager** tool, you will notice some more menus.

The **flag** icon is a notification area. Here we will find alerts, warnings, and informational messages about tasks we are running. Currently there is nothing there but keep an eye on this flag for a warning or error icon. Often you will find useful information here to solve a problem or complete a task.

![](data:image/png;base64...)

From the **Manage** menu we can Add or Remove Server Roles and Features, as well as, add servers to manage on our network.

![](data:image/png;base64...)

The **Tools** menu is a quick access list to our **Administrative Tools**. New tools for Server Roles will appear here when they are installed.

![](data:image/png;base64...)

# Part 3: Administrative Tools

Windows Server provides many GUI based tools for administrative task that we can perform on our systems. These are known as the Administrative Tools. As we expand the Server Roles of our system, new Administrative Tools will be added.

* Click on the **Start Menu**, then choose the **Windows Administrative** tools from the quick access tiles.

![](data:image/png;base64...)

A new window will appear with a list of all the installed Administrative Tools. As you can see there are quite a few of them, some beyond the scope of this introductory lesson. There is one tool here that is extremely useful as it incorporates many of the other tools into one.

* Double click on the **Computer Management** icon.

![](data:image/png;base64...)

The Computer Management tool is a prebuilt Microsoft Management Console (MMC). MMCs allow you to custom build you own tool sets for related tasks.

In the computer management tool, you will see several of the Administrative tools. Here are the highlights of some of the more useful tools:

* Click on the **Task Scheduler**.

The Task Schedule allows you to schedule common tasks to run on a specified schedule. This includes things like backups, updates, cleaning temporary folders, or running scripts.

* Click on the **Event Viewer**.
* Click the **Arrow** to expand
* Click the **Arrow** to expand **Windows Logs**
* Click on **Application**

The Event Viewer contains logs for many different aspects of the operating system. The Application logs show information for any applications installed. The Security logs show security audit information, such as log in and log out times. The System log show information and errors related to the OS. There are many other logs under Applications and Services that can be configured as well. This is a good place to start your troubleshooting.

* Expand **Services and Applications**
* Click on **Services**

Services are small programs or groups of programs that run in the background of your system provided specific functionality. Here we can find information and manage each of the services.

Some of the other tools here will be covered in future lab assignments.

# Part 4: Control Panel

The Control Panel contains another set of GUI tools provided by Windows. These tools allow use to control the settings of the operating system.

* Click on the **Start Menu** icon.
* Select the **Control Panel** from the quick access tiles.

![](data:image/png;base64...)

By default, the control panel opens in Category view. From here you can select different categories of settings, such as System and Security or Hardware. Many prefer the icon view, where each tool is listed individually.

* Click the **View by** drop down in the top right to switch to the **large icons** view.

![](data:image/png;base64...)

Large Icons View:

![](data:image/png;base64...)

Once again, there are quite a few tools here. Let’s go through some of the more commonly used tools.

* Click on **Device Manager**.

The Device Manager tools displays a list of all the hardware the operating system detected and is currently managing. You can double click on each piece of hardware to get more information and update driver software. Windows is usually pretty good about downloaded drivers from online sources, but sometimes you need to manually update the drivers for 3rd party hardware.

* Click on **Network and Sharing Center.**

The Network and Sharing Center is where you can control network related settings. For example, you can change the IP Address of your network interface card or setup up a VPN connection.

* Click on **Programs and Features.**

In Programs and Features, you can uninstall or change installation options of 3rd party applications as well as turn Windows features on or off.

* Click on **Windows Firewall.**

A firewall protects our system from unwanted network traffic, but sometimes you need to manually allow or block certain applications. The Windows Firewall tool allows us to create rules about what type of network traffic is allowed access our system.

**A lot of the settings that can be configured through the Control Panel can also be controlled through the newer Windows Settings tool, which can be found under the start menu.**

# Part 6: Windows Registry

The Control Panel tools are good for most common settings changes for the Windows operating system, but not every setting can be managed through these tools. This is when the Windows Registry can come in handy.

The registry is a central repository for settings and contains every setting for the system, installed applications, and users. By changing keys and values in the registry, we can make very specific changes to our operating system.

**The registry is not a place to play around. It is very easy to make a mistake that could break the functionality of the OS or applications. Be sure to only make changes to registry settings with specific instructions.**

* Search your system for the **Regedit** tool.

![](data:image/png;base64...)

When the registry tool opens, it looks somewhat like a file browser. Each of these “folders” are known as **Keys**. There are five top level Keys (sometimes referred to as **HIVES**), each of which contain **Sub Keys**. Sub Keys often have several Sub Keys themselves. At the lowest level of the registry, we have **Values**. Each Value contains **Data**. Values control the settings. The combination of Keys, Sub Keys, and Values is known as a **Registry Path**.

![](data:image/png;base64...)

**Each HIVE controls a different aspect of the operating system as follows:**

**HKEY\_CLASSES\_ROOT - Registry entries subordinate to this key define types (or classes) of documents and the properties associated with those types. Shell and COM applications use the information stored under this key.**

**HKEY\_CURRENT\_USER - Registry entries subordinate to this key define the preferences of the current user. These preferences include the settings of environment variables, data about program groups, colors, printers, network connections, and application preferences.**

**HKEY\_LOCAL\_MACHINE - Registry entries subordinate to this key define the physical state of the computer, including data about the bus type, system memory, and installed hardware and software.**

**HKEY\_USERS – Registry entries subordinate to this key define the default user configuration for new users on the local computer and the user configuration for the current user.**

**HKEY\_CURRENT\_CONFIG - Contains information about the current hardware profile of the local computer system.**

* Click on the arrow to expand **HKEY\_CURRENT\_USER.**
* Expand the Subkey **Control Panel**
* Click on the Subkey **Desktop**

![](data:image/png;base64...)

Here you will see the values related to settings for the currently logged in user’s desktop. Each value has a **name**, **type**, and **data**.

The type of value indicates the type of data that can be entered. There are several types that can be specified. Here are a few of the more common types:

**REG\_BINARY – Binary data in any form (1’s and 0’s)**

**REG\_DWORD – A 32-bit number**

**REG\_QWORD – A 64-bit number**

**REG\_SZ – A string value. (Letters, numbers, and characters. Cannot be null)**

**REG\_MULTI\_SZ – A sequence of string values.**

* Find the value with the name **WallPaper**.
* Double click the value to edit.

The data type for this value is a string. In this case it is a path to a file that is displayed as the desktop wall paper.

* Change the **Value Data** to **C:\Windows\Web\Wallpaper\Windows 10\img2.jpg**
* Click **OK** to save.
* Sign out of your system and then sign back in.

The Desktop background image changed because we changed the image that it was displaying in the registry settings.

Now it’s time to complete the Assessment for Lab 2. Use your system to capture any screen shots requested.



# Introduction

Installing an operating system is just the first step. What we have now is often referred to as a “vanilla” OS, which means we have a default installation. However, each system we setup is going to have different needs and configurations. Before we can start configuring the server, we need to learn about the tools we can use.

In this lab you will explore the many tools that Windows provides with the operating system to control and configure the system to our needs. Microsoft does a pretty good job at developing GUI based tools for most tasks, so for now we will focus on those.

# Part 1: Basic Navigation

Log into the **Windows Server** as **Administrator**

**When we first log into Windows Server, the Server Manager application automatically starts up. This is a useful tool that we will learn about later, but you can close the window for now.**

If you are a Windows 10 user, the screen show below should look familiar. This is known as the Desktop and is a user workspace. On the main part of the desktop, windows for programs that have GUI interfaces will appear. You can also save shortcuts to commonly used programs on the Desktop for easy access. On the bottom of the screen, highlighted in red, is the task bar. Here you will find several useful tools:

* Circled in orange is the Start Menu. Here you can find a list of all applications installed on the system.
* Circled in yellow is the search icon. You can quickly search for applications, files, or even the web from here.
* Circled in blue is Internet Explorer. This is an application that allow you to browse the internet. It’s not a good idea to browse the internet from a server and this version of Internet Explorer has a lot of security turned on.
* Circled in green is the Windows File Explorer. This application allows you to browse folders, files, and disks attached to your system. We will look at this in more depth in Lab 3.
* Circled in purple is the Notification Tray. Here you will find helpful information, such as alerts and programs that run in the background.

![](data:image/jpeg;base64...)

* Click the **Start Menu** icon.

The Start Menu has three distinct areas:

* In red, you will find icons that allow you:
  + Sign-out or switch users
  + Quickly access the settings
  + Power off or restart the system
* In green is the all programs list. This is an alphabetical list of all applications and tools installed on the system.
* In blue is the quick access tiles. There are commonly used programs. You can customize what shows up here.

![](data:image/png;base64...)

* Click the **Action Center icon** on the far right of the task bar.

In the Action Center, you will see alerts for your system and be able to quickly access network and other settings. You can see that my system currently needs some updates.

![](data:image/png;base64...)

* Right click on the **task bar**.

This will bring up another hidden menu that has option that allow you to control the task bar and other settings. A very useful tool that can be found here is the Task Manager. This allows you to monitor and control services on the system.

![](data:image/png;base64...)

* Click on the **search icon**.
* Type in **Server Manager** in the search bar.

The search feature in Windows Server will quickly let you find applications and files.

* Click on the **Server Manager Desktop app** to open that tool again.

![](data:image/png;base64...)

# Part 2: Server Manager

The Server Manager tool is a very useful application that provides a central location to view information about our server and have quick access to many commonly used tools for administering our server roles and features. We can even use this tool to view and manage other Windows Servers on the network.

![](data:image/png;base64...)

On the left-hand side of the Server Manager, we have several different tabs:

**Dashboard** – This is a quick start view with some common task we can run and an overview of the status of our server and server roles. As you can see, there are some red alerts on the example system.

* Click on the **Local Server** tab.

**Local Server** – This is where we can view information about our server and quickly access tools for changing configurations as we saw in Lab 1.

* Scroll down on the Local Server window.

As we scroll down, we can see more information:

**Events** – This are log event log entries related to our system. These can be error messages, warnings, or just informational. This is a great place to start troubleshooting.

**Services** – This is a list of all the services installed on our system. We can quickly check the status, start, or stop services from here.

![](data:image/png;base64...)

* Scroll down further.

**Best Practices Analyzer and Performance** – There is no information here currently, but we could turn on some performance monitoring tools to gather information about how our system is running.

* Scroll to the bottom.

**Roles and Features** – Here we will see information about all the roles and features currently installed on our server.

![](data:image/png;base64...)

**The All Servers tab is like the local server tab. The difference is it will allow viewing of information and control over other servers on the network if we set them up. For now, we are only looking into a single server.**

* Click on the **File and Storage Services** tab.

![](data:image/png;base64...)

This tab is for a Server Role called File and Storage Services that is installed by default on our system. Here we can manage volumes, disks, and storage pools. In later labs we will use this tool to also manage file shares.

**As we install more Server Roles on to our server, more tabs will appear. Each tab will give use access to tools and information necessary to mange them.**

In the **top right corner** of the **Server Manager** tool, you will notice some more menus.

The **flag** icon is a notification area. Here we will find alerts, warnings, and informational messages about tasks we are running. Currently there is nothing there but keep an eye on this flag for a warning or error icon. Often you will find useful information here to solve a problem or complete a task.

![](data:image/png;base64...)

From the **Manage** menu we can Add or Remove Server Roles and Features, as well as, add servers to manage on our network.

![](data:image/png;base64...)

The **Tools** menu is a quick access list to our **Administrative Tools**. New tools for Server Roles will appear here when they are installed.

![](data:image/png;base64...)

# Part 3: Administrative Tools

Windows Server provides many GUI based tools for administrative task that we can perform on our systems. These are known as the Administrative Tools. As we expand the Server Roles of our system, new Administrative Tools will be added.

* Click on the **Start Menu**, then choose the **Windows Administrative** tools from the quick access tiles.

![](data:image/png;base64...)

A new window will appear with a list of all the installed Administrative Tools. As you can see there are quite a few of them, some beyond the scope of this introductory lesson. There is one tool here that is extremely useful as it incorporates many of the other tools into one.

* Double click on the **Computer Management** icon.

![](data:image/png;base64...)

The Computer Management tool is a prebuilt Microsoft Management Console (MMC). MMCs allow you to custom build you own tool sets for related tasks.

In the computer management tool, you will see several of the Administrative tools. Here are the highlights of some of the more useful tools:

* Click on the **Task Scheduler**.

The Task Schedule allows you to schedule common tasks to run on a specified schedule. This includes things like backups, updates, cleaning temporary folders, or running scripts.

* Click on the **Event Viewer**.
* Click the **Arrow** to expand
* Click the **Arrow** to expand **Windows Logs**
* Click on **Application**

The Event Viewer contains logs for many different aspects of the operating system. The Application logs show information for any applications installed. The Security logs show security audit information, such as log in and log out times. The System log show information and errors related to the OS. There are many other logs under Applications and Services that can be configured as well. This is a good place to start your troubleshooting.

* Expand **Services and Applications**
* Click on **Services**

Services are small programs or groups of programs that run in the background of your system provided specific functionality. Here we can find information and manage each of the services.

Some of the other tools here will be covered in future lab assignments.

# Part 4: Control Panel

The Control Panel contains another set of GUI tools provided by Windows. These tools allow use to control the settings of the operating system.

* Click on the **Start Menu** icon.
* Select the **Control Panel** from the quick access tiles.

![](data:image/png;base64...)

By default, the control panel opens in Category view. From here you can select different categories of settings, such as System and Security or Hardware. Many prefer the icon view, where each tool is listed individually.

* Click the **View by** drop down in the top right to switch to the **large icons** view.

![](data:image/png;base64...)

Large Icons View:

![](data:image/png;base64...)

Once again, there are quite a few tools here. Let’s go through some of the more commonly used tools.

* Click on **Device Manager**.

The Device Manager tools displays a list of all the hardware the operating system detected and is currently managing. You can double click on each piece of hardware to get more information and update driver software. Windows is usually pretty good about downloaded drivers from online sources, but sometimes you need to manually update the drivers for 3rd party hardware.

* Click on **Network and Sharing Center.**

The Network and Sharing Center is where you can control network related settings. For example, you can change the IP Address of your network interface card or setup up a VPN connection.

* Click on **Programs and Features.**

In Programs and Features, you can uninstall or change installation options of 3rd party applications as well as turn Windows features on or off.

* Click on **Windows Firewall.**

A firewall protects our system from unwanted network traffic, but sometimes you need to manually allow or block certain applications. The Windows Firewall tool allows us to create rules about what type of network traffic is allowed access our system.

**A lot of the settings that can be configured through the Control Panel can also be controlled through the newer Windows Settings tool, which can be found under the start menu.**

# Part 6: Windows Registry

The Control Panel tools are good for most common settings changes for the Windows operating system, but not every setting can be managed through these tools. This is when the Windows Registry can come in handy.

The registry is a central repository for settings and contains every setting for the system, installed applications, and users. By changing keys and values in the registry, we can make very specific changes to our operating system.

**The registry is not a place to play around. It is very easy to make a mistake that could break the functionality of the OS or applications. Be sure to only make changes to registry settings with specific instructions.**

* Search your system for the **Regedit** tool.

![](data:image/png;base64...)

When the registry tool opens, it looks somewhat like a file browser. Each of these “folders” are known as **Keys**. There are five top level Keys (sometimes referred to as **HIVES**), each of which contain **Sub Keys**. Sub Keys often have several Sub Keys themselves. At the lowest level of the registry, we have **Values**. Each Value contains **Data**. Values control the settings. The combination of Keys, Sub Keys, and Values is known as a **Registry Path**.

![](data:image/png;base64...)

**Each HIVE controls a different aspect of the operating system as follows:**

**HKEY\_CLASSES\_ROOT - Registry entries subordinate to this key define types (or classes) of documents and the properties associated with those types. Shell and COM applications use the information stored under this key.**

**HKEY\_CURRENT\_USER - Registry entries subordinate to this key define the preferences of the current user. These preferences include the settings of environment variables, data about program groups, colors, printers, network connections, and application preferences.**

**HKEY\_LOCAL\_MACHINE - Registry entries subordinate to this key define the physical state of the computer, including data about the bus type, system memory, and installed hardware and software.**

**HKEY\_USERS – Registry entries subordinate to this key define the default user configuration for new users on the local computer and the user configuration for the current user.**

**HKEY\_CURRENT\_CONFIG - Contains information about the current hardware profile of the local computer system.**

* Click on the arrow to expand **HKEY\_CURRENT\_USER.**
* Expand the Subkey **Control Panel**
* Click on the Subkey **Desktop**

![](data:image/png;base64...)

Here you will see the values related to settings for the currently logged in user’s desktop. Each value has a **name**, **type**, and **data**.

The type of value indicates the type of data that can be entered. There are several types that can be specified. Here are a few of the more common types:

**REG\_BINARY – Binary data in any form (1’s and 0’s)**

**REG\_DWORD – A 32-bit number**

**REG\_QWORD – A 64-bit number**

**REG\_SZ – A string value. (Letters, numbers, and characters. Cannot be null)**

**REG\_MULTI\_SZ – A sequence of string values.**

* Find the value with the name **WallPaper**.
* Double click the value to edit.

The data type for this value is a string. In this case it is a path to a file that is displayed as the desktop wall paper.

* Change the **Value Data** to **C:\Windows\Web\Wallpaper\Windows 10\img2.jpg**
* Click **OK** to save.
* Sign out of your system and then sign back in.

The Desktop background image changed because we changed the image that it was displaying in the registry settings.

Now it’s time to complete the Assessment for Lab 2. Use your system to capture any screen shots requested.


