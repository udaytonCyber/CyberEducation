
# Introduction

Windows Server was designed to provide many different network services without the need of installing third party software. These native services are known as **Server Roles**, which are often made up of several different processes and services that work together to provide functionality. These processes and services individually are known as **Role Services**. Along with the Role Services that can are installed with each Server Role, you can add **Features**, which add or augment the functionality of the Server Role. In this lab, we will walk through the necessary tools and steps need to install and configure the network and install a Server Role.

# Part One: Configuring the Network

Before we set anything else up, let’s make sure are network settings are configured correctly.

* On the left-hand side of **Server Manager**, choose **Local Server** to access the **server properties**.
* Find the network information next to **Ethernet**.

Currently we are assigned an IP address through **DHCP**. Since DHCP assigned network settings on a time-based lease, it is possible those setting could change. We should set a **static IP address**.

* Click the **link** next to **Ethernet**.

![](data:image/png;base64...)

This will open our **network connections**. In the example system, we have just one Ethernet connection to the network.

* **Right click** the **icon** for the connection.
* Choose **Status**.

![](data:image/png;base64...)

* On the **status window**, click the **Details** button.

![](data:image/png;base64...)

This will show the **Network Connection Details** window. Here we can see what the current settings are.

![](data:image/png;base64...)

**Normally you would get the static network setting from the Network Administrator, but for our purposes, we will simply reuse what was automatically assigned to us.**

* Take note of the following settings (yours will be different than the example):
  + **IPv4 Address**
  + **IPv4 Subnet Mask**
  + **IPv4 Default Gateway**
  + **IPv4 DNS Servers**
* **Close** the **network connection details** window.
* On the **Status window**, click **Properties**.
* Highlight the **Internet Protocol Version 4 (TCP/IPv4)** item.
* Click **Properties**.

![](data:image/png;base64...)

In the **Internet Protocol Version 4 (TCP/IPv4) Properties** window we can set our static network settings.

* Choose **Use the following IP Address**.
* Enter the information you recorded above.
* Choose **Use the following DNS server Addresses**.
* Enter the DNS server addresses you recorded above.

![](data:image/png;base64...)

* Click **OK**.
* Close the **Ethernet Properties window**.
* Close the **Ethernet Status window**.
* Click the **refresh icon** in **Server Manager**.

You should see your static IP address now in the settings.

![](data:image/png;base64...)

Next, we should set an easy to remember, yet unique **Computer name**.

* Click the **link** next to **Computer name**.
* In the **System Properties window**, click **Change**.
* Under **Computer name**, enter the name **<username>-win** (replace <username> with your username.)

![](data:image/png;base64...)

* Click **Ok.**
* Close the **System Properties window.**
* It will prompt you to restart the system. Click **Restart Now** to apply the change.
* After the system reboots, log in again.

1. **Save a screen shot of the Server Manager local server properties page showing the new Computer name and IP address to upload for the lab assessment.**

# Part Two: Installing a Role

Installing a new **Server Role and Features** on to a **Windows Server 2016** can be accomplished using Wizards. **Wizards** are GUI based guides that help you choose the correct options to install software. If you have every installed any software in a graphical user interface, it is likely you have used a Wizard.

**One common mistake many make when using a Wizard is to click next, next, next…without reading the information presented to them. As a systems administrator you should know exactly what is being installed on your system, so it is important to read through the Wizards menus. A simple missed checkbox could create needless problems down the road.**

To access the **Add Roles and Features Wizard**, we can use the **Server Manager Dashboard**.

* From the **Manage** menu in the top right corner, choose **“Add Roles and Features”.**

You will be presented with the **“Before you begin”** page. This page instructs you to make sure a few tasks are completed. One of which is to insure you have a static IP address configured. You should also make sure all updates are installed before installing a new Role.

![](data:image/png;base64...)

* Click **Next.**

The **Select installation** type page give you two options:

![](data:image/png;base64...)

For our purposes, we will only use the **Role-based or feature-based installation**.

* Click **Next**.

The **Select destination server** page allows use to select a server. It is possible to use this tool to install Server Roles on remote computers. We only have one option here.

![](data:image/png;base64...)

* Click **Next**.

Next, we can **Select server roles to install**. For this example, we will install the **Print and Document Services** roles.

* Select the **Print and Document Services** role.

![](data:image/png;base64...)

* When prompted, click **Add Features** to add the default features to the installation.

![](data:image/png;base64...)

**Some roles come with their own management tools, these are considered features and will be installed into the Administrative Tools menu.**

* Click **Next**.

On the **Select features page**, we can choose to add additional features if needed. We will not add any at this time.

![](data:image/png;base64...)

* Click **Next.**

The next page is a description of the Server Role we are about to install. There may be important things to note here.

![](data:image/png;base64...)

* Click **Next.**

The next screen gives us the option to select the role services we would like to install with this Server Role. For now, we will just accept the default of **Print Server**.

![](data:image/png;base64...)

Click **Next.**

Finally, we have the **Confirmation page**. This will give a chance to confirm our choices.

![](data:image/png;base64...)

* Click **Install**.

The results screen will show the progress of the installation. This will take a moment or two.

* Once the installation is complete, you may click **close**.

![](data:image/png;base64...)

Take note that a new Tab has been added to the left-hand side of the Server Manager for Print Services. These tabs we will use later to configure our Roles.

* Click on the **Print Services Tab** on the left-hand side.

1. **Save a screen shot of the Print Services page for the lab assessment.**


# Introduction

Windows Server was designed to provide many different network services without the need of installing third party software. These native services are known as **Server Roles**, which are often made up of several different processes and services that work together to provide functionality. These processes and services individually are known as **Role Services**. Along with the Role Services that can are installed with each Server Role, you can add **Features**, which add or augment the functionality of the Server Role. In this lab, we will walk through the necessary tools and steps need to install and configure the network and install a Server Role.

# Part One: Configuring the Network

Before we set anything else up, let’s make sure are network settings are configured correctly.

* On the left-hand side of **Server Manager**, choose **Local Server** to access the **server properties**.
* Find the network information next to **Ethernet**.

Currently we are assigned an IP address through **DHCP**. Since DHCP assigned network settings on a time-based lease, it is possible those setting could change. We should set a **static IP address**.

* Click the **link** next to **Ethernet**.

![](data:image/png;base64...)

This will open our **network connections**. In the example system, we have just one Ethernet connection to the network.

* **Right click** the **icon** for the connection.
* Choose **Status**.

![](data:image/png;base64...)

* On the **status window**, click the **Details** button.

![](data:image/png;base64...)

This will show the **Network Connection Details** window. Here we can see what the current settings are.

![](data:image/png;base64...)

**Normally you would get the static network setting from the Network Administrator, but for our purposes, we will simply reuse what was automatically assigned to us.**

* Take note of the following settings (yours will be different than the example):
  + **IPv4 Address**
  + **IPv4 Subnet Mask**
  + **IPv4 Default Gateway**
  + **IPv4 DNS Servers**
* **Close** the **network connection details** window.
* On the **Status window**, click **Properties**.
* Highlight the **Internet Protocol Version 4 (TCP/IPv4)** item.
* Click **Properties**.

![](data:image/png;base64...)

In the **Internet Protocol Version 4 (TCP/IPv4) Properties** window we can set our static network settings.

* Choose **Use the following IP Address**.
* Enter the information you recorded above.
* Choose **Use the following DNS server Addresses**.
* Enter the DNS server addresses you recorded above.

![](data:image/png;base64...)

* Click **OK**.
* Close the **Ethernet Properties window**.
* Close the **Ethernet Status window**.
* Click the **refresh icon** in **Server Manager**.

You should see your static IP address now in the settings.

![](data:image/png;base64...)

Next, we should set an easy to remember, yet unique **Computer name**.

* Click the **link** next to **Computer name**.
* In the **System Properties window**, click **Change**.
* Under **Computer name**, enter the name **<username>-win** (replace <username> with your username.)

![](data:image/png;base64...)

* Click **Ok.**
* Close the **System Properties window.**
* It will prompt you to restart the system. Click **Restart Now** to apply the change.
* After the system reboots, log in again.

1. **Save a screen shot of the Server Manager local server properties page showing the new Computer name and IP address to upload for the lab assessment.**

# Part Two: Installing a Role

Installing a new **Server Role and Features** on to a **Windows Server 2016** can be accomplished using Wizards. **Wizards** are GUI based guides that help you choose the correct options to install software. If you have every installed any software in a graphical user interface, it is likely you have used a Wizard.

**One common mistake many make when using a Wizard is to click next, next, next…without reading the information presented to them. As a systems administrator you should know exactly what is being installed on your system, so it is important to read through the Wizards menus. A simple missed checkbox could create needless problems down the road.**

To access the **Add Roles and Features Wizard**, we can use the **Server Manager Dashboard**.

* From the **Manage** menu in the top right corner, choose **“Add Roles and Features”.**

You will be presented with the **“Before you begin”** page. This page instructs you to make sure a few tasks are completed. One of which is to insure you have a static IP address configured. You should also make sure all updates are installed before installing a new Role.

![](data:image/png;base64...)

* Click **Next.**

The **Select installation** type page give you two options:

![](data:image/png;base64...)

For our purposes, we will only use the **Role-based or feature-based installation**.

* Click **Next**.

The **Select destination server** page allows use to select a server. It is possible to use this tool to install Server Roles on remote computers. We only have one option here.

![](data:image/png;base64...)

* Click **Next**.

Next, we can **Select server roles to install**. For this example, we will install the **Print and Document Services** roles.

* Select the **Print and Document Services** role.

![](data:image/png;base64...)

* When prompted, click **Add Features** to add the default features to the installation.

![](data:image/png;base64...)

**Some roles come with their own management tools, these are considered features and will be installed into the Administrative Tools menu.**

* Click **Next**.

On the **Select features page**, we can choose to add additional features if needed. We will not add any at this time.

![](data:image/png;base64...)

* Click **Next.**

The next page is a description of the Server Role we are about to install. There may be important things to note here.

![](data:image/png;base64...)

* Click **Next.**

The next screen gives us the option to select the role services we would like to install with this Server Role. For now, we will just accept the default of **Print Server**.

![](data:image/png;base64...)

Click **Next.**

Finally, we have the **Confirmation page**. This will give a chance to confirm our choices.

![](data:image/png;base64...)

* Click **Install**.

The results screen will show the progress of the installation. This will take a moment or two.

* Once the installation is complete, you may click **close**.

![](data:image/png;base64...)

Take note that a new Tab has been added to the left-hand side of the Server Manager for Print Services. These tabs we will use later to configure our Roles.

* Click on the **Print Services Tab** on the left-hand side.

1. **Save a screen shot of the Print Services page for the lab assessment.**

