
# Introduction

One of the most important tasks of an operating system is file management. Files are digitized containers that hold data. This data could be a budget plan in an excel spread sheet, a pdf file with your tax return, a binary executable file for a program, or a shared library of data for the OS to manage multiple applications. Files can be organized using folders (some time referred to as directories). Each folder can contain subfolders and/or files. Regardless of the contents of the file, each and everyone serves a purpose to the user, an application, the OS, or a hardware device. Keeping files organized is essential to the functionality of a computer system.

# Part 1: Windows File Structure

Many other popular operating systems such as Linux and MAC OSX, use a file structure that is based off the Unix file structure. (You’ll learn more about that in Module 3). Windows has a unique file structure that some find easier to navigate.

One of the most notable differences is Windows use of drive letters. Each hard drive, partition, DVD drive, or any other storage device is given its own drive letter. By default, the C:\ drive refers to the OS boot drive and is sometimes referred to as the root drive. Other drives are assigned letters following C:\ from when they are attached, although you can manually select a drive letter that you prefer.

* Log into your **Windows Server**.
* Open the **Windows File Explorer** from the **Task Bar**.
* Click on the **This PC** Icon to view all the drives attached to your computer.

**The reason the default hard drive is labeled C:\ is because before hard drives were common place back in the days of Microsoft DOS, computers generally had two floppy drives, one for the OS and one to load programs or save data too. These were always assigned A:\ and B:\ by default. Floppy disk drives are rarely seen anymore, but this convention stuck.**

![](data:image/png;base64...)

You can see from the image above that this computer does have a floppy drive (A:/) and a DVD Drive (D:/) attached. If you were to insert a USB flash drive, it would automatically get the letter E:/.

Each drive also gets a human readable label, such as Local Disk for the OS drive. This can be manually change.

* Double click on the C:\ drive to view the directories at the top level.

![](data:image/png;base64...)

On the Windows OS drive, the operating system creates several directories during the installation process. Each one of these has a special purpose and contains specific subfolders and files. By default, we can only see a few of these directories, but there are more that are hidden from normal users view.

* Click on the **View** menu and find the check box for **Hidden Items.**

![](data:image/png;base64...)

By checking this box, we enable the user to view the hidden files and folders. For an IT technician this may be necessary to find certain configuration and log files for applications.

![](data:image/png;base64...)

Notice there is now a new directory called ProgramData. The slightly opaque folder indicates that this is a hidden folder.

Each of these top-level folders has a special function and some have key subfolders beneath them.

**PerfLogs** – This folder is for storing performance logs. It generally will be empty unless you turn on performance monitoring.

**Program Files** – In 64-bit version of windows, this is where 64-bit applications are installed. In older 32-bit versions of windows, all applications were installed here. Since we haven’t installed any 3rd party applications, everything is from Windows.

* Open the **Program Files** directory by double clicking it.

![](data:image/png;base64...)

* Click the **up arrow** next the directory path or click on the **Local Disk (C:)** to go back up one level.

**Program Files (x86)** – 64-bit versions of windows use this directory to install 32-bit applications for backwards compatibility.

**ProgramData (hidden)** – This directory can be used by applications to store files that it creates during its use. These can be temporary files or often this is were you will find log files for applications.

**Users** – This directory contains profile settings, documents, Desktop files, and anything else the user wishes to store. Each user gets their own folder that can only be accessed by them and any administrators on the system.

* Double click the **Users** directory to view the different sub directories.

![](data:image/png;base64...)

Currently this system only has one user, the Administrator. The **Default** folder contains the default user profile that will be applied to all new users. The **Pubic** folder is where you can save files and settings that are available to all users of the system.

* Open the **Administrator** user’s folder.

![](data:image/png;base64...)

Each user has a set of directories created by default, designed to hold common types of data. Each of these directories have a special icon instead of a folder, but function just the same. Windows does not limit what you can save to any of these directories, but they often link to Quick access bars in the File explorer and other applications.

There is a hidden **AppData** folder here as well. This folder can be used by applications to store information the is unique to a user, often settings files.

* Change back the **Local Disk (C:)** directory by clicking on the name in the address bar.
* Open the **Windows** folder to view the contents.

The Windows folder contains all the operating system folders and files. As you can see there is quite a bit in here. The three most notable sub folders in the Windows directory are the system folders; C:\System, C:\System32, and C:\SystemWOW64.

Each of these directories contain dynamic-link library files that implement core features of Windows and allow applications to load specific features through Windows API.

**It is generally not a good idea to manually make changes to any of the default directories other the users directory. Making a change or deleting a file could cause and application or the entire system to stop working. There may be times when it is necessary to edit within these directories but follow any instructions carefully.**

Another important concept to understand about directories, sub directories, and files is the **file path**. The **file path** acts like a map for the system on how to find a specific file and must be exact. A file path uses a structure similar to **C:\Dir1\Dir2\File1.txt**

Use the file path **C:\Windows\System32\drivers\etc\hosts** to locate the “hosts” file. Save a screen shot showing the file for the Lab 3 assessment.

**Hint: You can enter the file path in the to address bar or click your way through all the files.**

# Part 2: Working with Windows Files and Directories

No matter what the purpose of the system you are configuring, there is a good chance that some file management will be necessary. Perhaps it’s a user workstation where you are saving Excel spread sheets or maybe a shared file server where users are collaborating on a Power Point presentation. Either way, creating files will be a key function of the operating system administrator. Keeping files organized in directories makes it easier to find files you need to work on.

Most Windows applications, like Microsoft Office will create and save files through the application itself, however, we still need to know how to manipulate them through the OS. In the case of Window, we will use Windows File Explorer.

* Open **Windows File Explorer** on your system.
* Click on **Documents** on the left-hand side.

This will open the Documents directory for the currently logged in user.

![](data:image/png;base64...)

There is nothing currently in this folder. Let’s add some directories to keep things organized.

* Right click anywhere in the white space.
* Hover your mouse over **New**.
* Hover your mouse over **Folder**.
* Type the name **Work** next to the folder.
* Repeat the steps to create two more folders named **Taxes** and **PartyPlanning.**

![](data:image/png;base64...)

We can also create directories within directories. This is known as nesting folders.

* Open the **Taxes** folder
* Create three new directories named **2017, 2018, and 2019.**

![](data:image/png;base64...)

Whoops! We haven’t done our 2019 taxes yet, that should be 2016! To fix this, we need to rename the folder.

* Right click on the **2019** folder.
* Hover you mouse over **Rename** and click.
* Type **2016**.

![](data:image/png;base64...)

**Notice the file moved to the top. This is because by default Windows sorts files and folders in a descending order (or alphabetical if they had words for names.)**

Notice there are other option under the right click menu as well. We will cover some of these in a minute.

Now that we have learned to create directories, lets work with some files. You’ll notice the process is similar.

* Go back to the **Documents** folder.
* Open the **PartyPlanning** folder.
* Right click in the white space.
* Hover you mouse over **New.**
* Hover you mouse over **Text Document**.
* Enter the name **Gift Ideas.**
* Hit **Enter.**

![](data:image/png;base64...)

* Create another file named **Guest List**, but this time choose **Rich Text Document**.
* Create another file named **Party Locations**, but this time choose **Bitmap image**.

![](data:image/png;base64...)

**Notice these new files have different icons and a different type. We will talk more about this in the next section.**

* Let’s practice a little more. Create the following text files in the **Work** directory:
  + **Budget**
  + **Payroll**
  + **Employee List**
  + **Party Budget**

Now let’s look at moving files around to keep things organized. For example, the accounts have requested a copy of the Payroll file be placed in the 2018 taxes folder. We can do this using the copy and paste functionality.

* Right click on the **Payroll** folder and click on **Copy.**
* Open the **Taxes\2018** folder.
* Right click in the white space and click on **Paste**.

A new copy of the file appears. The original file will still be kept in the Work folder.

The Party Budget file doesn’t belong on the Work folder and should be moved to the PartyPlanning folder. We can accomplish this by using the cut and paste functionality.

* Navigate back to the **Work** folder.
* Right click on the **Party Budget** file.
* Click on **Cut**.
* Navigate to the **PartyPlanning** folder.
* Right click in the white space.
* Click on **Paste**.

This time the file appears in PartyPlanning but was removed from Work.

We can do the same operations to folders as well.

* Right click on the **Taxes** folder and choose **Cut**.
* Open the **Work** folder and click **Paste**.

The **Taxes** directory, all of child directories (**2016,2017, & 2018**), as well as the files in all directories have been moved to the **Work** directory.

**Keyboard shortcuts make life a lot easier and Cut, Copy, and Paste have some of the most popular keyboard shortcuts. Ctrl-X, Ctrl-C, and Ctrl-V will preform these steps respectively. These shortcuts work with most operating systems and programs.**

Of course, now we have two copies of the **Payroll** file. To save space, let’s delete the copy in the **Work** folder.

* Right click on the **Payroll** file.
* Click **Delete**.

Now that file has been removed. Or has it? Windows has a nice feature called the Recycle Bin. When ever you delete a file with the GUI, it doesn’t remove the file completely, but rather moves it to a special directory named Recycle Bin that can be found on your desktop.

* Minimize all windows and go to the **Desktop**.
* Double click the **Recycle Bin** icon.

![](data:image/png;base64...)

Here lie all deleted files. If we deleted one by mistake we can restore it.

* Right click on the **Payroll** file.
* Click **Restore**.
* Navigate back to the **Work** folder.

The file is restored back to its original location.

* Take a screen shot of the Documents folder within Windows File Explorer. Save this to upload during lab assessment 3.

Windows will keep all files in the recycle bin indefinitely. However, it is a good practice to clear the recycle bin once and a while. If these files are truly no longer needed, no need to have them taking up space on your system.

# Part 3: Windows File Extensions

A file extension is a way for both the user and the operating system to identify the type of data that is contained in the file. This helps determine which application to opens the file or if it is a system file. You may be familiar with some of the commonly used file extensions:

* .docx – Microsoft Word file
* .xlsx – Microsoft Excel file
* .ppt – Power Point file
* .pdf – Adobe PDF file
* .exe – Executable application file

And many more!

In the previous section, we create three different types of files:

Text Document

Rich Text Document

Bitmap Image

Each of these have different file extensions, but by default Windows hides these.

* Navigate to and open the **PartyPlanning** folder.
* Click on the **View** menu in **File Explorer**.
* Find the check box for **File** name extensions and click it.

![](data:image/png;base64...)

Now the file extensions are visible with the file names.

![](data:image/png;base64...)

* The Text Documents use the file extension .txt
* The Rich Text Document uses the file extension .rtf
* And the Bitmap image uses the file extension .bmp

If we change the file extension, it will change how the operating system identifies and handles the file.

* Double click the **Gift Ideas.txt** file

Since this is a .txt file it opens in Notepad, windows default text editor.

* Double click the **Guest List.rtf** file.

Rich Text format files cannot be opened with notepad because they have more formatting options. Therefore, this file is opened in WordPad.

* Double click the **Partly Locations.bmp** file.

A bitmap is an image (picture) file, so it opens in Microsoft Paint.

* Rename the **Gift Ideas.txt** file to **Gift Ideas.html**
* Click **Yes** to acknowledge the change.

Notice the icon changed for this file. Windows now sees this as an html file, which is a web site file.

* Double click the file now.

Since Windows sees this as a web site file, it tries to open it up in Internet Explorer.



# Introduction

One of the most important tasks of an operating system is file management. Files are digitized containers that hold data. This data could be a budget plan in an excel spread sheet, a pdf file with your tax return, a binary executable file for a program, or a shared library of data for the OS to manage multiple applications. Files can be organized using folders (some time referred to as directories). Each folder can contain subfolders and/or files. Regardless of the contents of the file, each and everyone serves a purpose to the user, an application, the OS, or a hardware device. Keeping files organized is essential to the functionality of a computer system.

# Part 1: Windows File Structure

Many other popular operating systems such as Linux and MAC OSX, use a file structure that is based off the Unix file structure. (You’ll learn more about that in Module 3). Windows has a unique file structure that some find easier to navigate.

One of the most notable differences is Windows use of drive letters. Each hard drive, partition, DVD drive, or any other storage device is given its own drive letter. By default, the C:\ drive refers to the OS boot drive and is sometimes referred to as the root drive. Other drives are assigned letters following C:\ from when they are attached, although you can manually select a drive letter that you prefer.

* Log into your **Windows Server**.
* Open the **Windows File Explorer** from the **Task Bar**.
* Click on the **This PC** Icon to view all the drives attached to your computer.

**The reason the default hard drive is labeled C:\ is because before hard drives were common place back in the days of Microsoft DOS, computers generally had two floppy drives, one for the OS and one to load programs or save data too. These were always assigned A:\ and B:\ by default. Floppy disk drives are rarely seen anymore, but this convention stuck.**

![](data:image/png;base64...)

You can see from the image above that this computer does have a floppy drive (A:/) and a DVD Drive (D:/) attached. If you were to insert a USB flash drive, it would automatically get the letter E:/.

Each drive also gets a human readable label, such as Local Disk for the OS drive. This can be manually change.

* Double click on the C:\ drive to view the directories at the top level.

![](data:image/png;base64...)

On the Windows OS drive, the operating system creates several directories during the installation process. Each one of these has a special purpose and contains specific subfolders and files. By default, we can only see a few of these directories, but there are more that are hidden from normal users view.

* Click on the **View** menu and find the check box for **Hidden Items.**

![](data:image/png;base64...)

By checking this box, we enable the user to view the hidden files and folders. For an IT technician this may be necessary to find certain configuration and log files for applications.

![](data:image/png;base64...)

Notice there is now a new directory called ProgramData. The slightly opaque folder indicates that this is a hidden folder.

Each of these top-level folders has a special function and some have key subfolders beneath them.

**PerfLogs** – This folder is for storing performance logs. It generally will be empty unless you turn on performance monitoring.

**Program Files** – In 64-bit version of windows, this is where 64-bit applications are installed. In older 32-bit versions of windows, all applications were installed here. Since we haven’t installed any 3rd party applications, everything is from Windows.

* Open the **Program Files** directory by double clicking it.

![](data:image/png;base64...)

* Click the **up arrow** next the directory path or click on the **Local Disk (C:)** to go back up one level.

**Program Files (x86)** – 64-bit versions of windows use this directory to install 32-bit applications for backwards compatibility.

**ProgramData (hidden)** – This directory can be used by applications to store files that it creates during its use. These can be temporary files or often this is were you will find log files for applications.

**Users** – This directory contains profile settings, documents, Desktop files, and anything else the user wishes to store. Each user gets their own folder that can only be accessed by them and any administrators on the system.

* Double click the **Users** directory to view the different sub directories.

![](data:image/png;base64...)

Currently this system only has one user, the Administrator. The **Default** folder contains the default user profile that will be applied to all new users. The **Pubic** folder is where you can save files and settings that are available to all users of the system.

* Open the **Administrator** user’s folder.

![](data:image/png;base64...)

Each user has a set of directories created by default, designed to hold common types of data. Each of these directories have a special icon instead of a folder, but function just the same. Windows does not limit what you can save to any of these directories, but they often link to Quick access bars in the File explorer and other applications.

There is a hidden **AppData** folder here as well. This folder can be used by applications to store information the is unique to a user, often settings files.

* Change back the **Local Disk (C:)** directory by clicking on the name in the address bar.
* Open the **Windows** folder to view the contents.

The Windows folder contains all the operating system folders and files. As you can see there is quite a bit in here. The three most notable sub folders in the Windows directory are the system folders; C:\System, C:\System32, and C:\SystemWOW64.

Each of these directories contain dynamic-link library files that implement core features of Windows and allow applications to load specific features through Windows API.

**It is generally not a good idea to manually make changes to any of the default directories other the users directory. Making a change or deleting a file could cause and application or the entire system to stop working. There may be times when it is necessary to edit within these directories but follow any instructions carefully.**

Another important concept to understand about directories, sub directories, and files is the **file path**. The **file path** acts like a map for the system on how to find a specific file and must be exact. A file path uses a structure similar to **C:\Dir1\Dir2\File1.txt**

Use the file path **C:\Windows\System32\drivers\etc\hosts** to locate the “hosts” file. Save a screen shot showing the file for the Lab 3 assessment.

**Hint: You can enter the file path in the to address bar or click your way through all the files.**

# Part 2: Working with Windows Files and Directories

No matter what the purpose of the system you are configuring, there is a good chance that some file management will be necessary. Perhaps it’s a user workstation where you are saving Excel spread sheets or maybe a shared file server where users are collaborating on a Power Point presentation. Either way, creating files will be a key function of the operating system administrator. Keeping files organized in directories makes it easier to find files you need to work on.

Most Windows applications, like Microsoft Office will create and save files through the application itself, however, we still need to know how to manipulate them through the OS. In the case of Window, we will use Windows File Explorer.

* Open **Windows File Explorer** on your system.
* Click on **Documents** on the left-hand side.

This will open the Documents directory for the currently logged in user.

![](data:image/png;base64...)

There is nothing currently in this folder. Let’s add some directories to keep things organized.

* Right click anywhere in the white space.
* Hover your mouse over **New**.
* Hover your mouse over **Folder**.
* Type the name **Work** next to the folder.
* Repeat the steps to create two more folders named **Taxes** and **PartyPlanning.**

![](data:image/png;base64...)

We can also create directories within directories. This is known as nesting folders.

* Open the **Taxes** folder
* Create three new directories named **2017, 2018, and 2019.**

![](data:image/png;base64...)

Whoops! We haven’t done our 2019 taxes yet, that should be 2016! To fix this, we need to rename the folder.

* Right click on the **2019** folder.
* Hover you mouse over **Rename** and click.
* Type **2016**.

![](data:image/png;base64...)

**Notice the file moved to the top. This is because by default Windows sorts files and folders in a descending order (or alphabetical if they had words for names.)**

Notice there are other option under the right click menu as well. We will cover some of these in a minute.

Now that we have learned to create directories, lets work with some files. You’ll notice the process is similar.

* Go back to the **Documents** folder.
* Open the **PartyPlanning** folder.
* Right click in the white space.
* Hover you mouse over **New.**
* Hover you mouse over **Text Document**.
* Enter the name **Gift Ideas.**
* Hit **Enter.**

![](data:image/png;base64...)

* Create another file named **Guest List**, but this time choose **Rich Text Document**.
* Create another file named **Party Locations**, but this time choose **Bitmap image**.

![](data:image/png;base64...)

**Notice these new files have different icons and a different type. We will talk more about this in the next section.**

* Let’s practice a little more. Create the following text files in the **Work** directory:
  + **Budget**
  + **Payroll**
  + **Employee List**
  + **Party Budget**

Now let’s look at moving files around to keep things organized. For example, the accounts have requested a copy of the Payroll file be placed in the 2018 taxes folder. We can do this using the copy and paste functionality.

* Right click on the **Payroll** folder and click on **Copy.**
* Open the **Taxes\2018** folder.
* Right click in the white space and click on **Paste**.

A new copy of the file appears. The original file will still be kept in the Work folder.

The Party Budget file doesn’t belong on the Work folder and should be moved to the PartyPlanning folder. We can accomplish this by using the cut and paste functionality.

* Navigate back to the **Work** folder.
* Right click on the **Party Budget** file.
* Click on **Cut**.
* Navigate to the **PartyPlanning** folder.
* Right click in the white space.
* Click on **Paste**.

This time the file appears in PartyPlanning but was removed from Work.

We can do the same operations to folders as well.

* Right click on the **Taxes** folder and choose **Cut**.
* Open the **Work** folder and click **Paste**.

The **Taxes** directory, all of child directories (**2016,2017, & 2018**), as well as the files in all directories have been moved to the **Work** directory.

**Keyboard shortcuts make life a lot easier and Cut, Copy, and Paste have some of the most popular keyboard shortcuts. Ctrl-X, Ctrl-C, and Ctrl-V will preform these steps respectively. These shortcuts work with most operating systems and programs.**

Of course, now we have two copies of the **Payroll** file. To save space, let’s delete the copy in the **Work** folder.

* Right click on the **Payroll** file.
* Click **Delete**.

Now that file has been removed. Or has it? Windows has a nice feature called the Recycle Bin. When ever you delete a file with the GUI, it doesn’t remove the file completely, but rather moves it to a special directory named Recycle Bin that can be found on your desktop.

* Minimize all windows and go to the **Desktop**.
* Double click the **Recycle Bin** icon.

![](data:image/png;base64...)

Here lie all deleted files. If we deleted one by mistake we can restore it.

* Right click on the **Payroll** file.
* Click **Restore**.
* Navigate back to the **Work** folder.

The file is restored back to its original location.

* Take a screen shot of the Documents folder within Windows File Explorer. Save this to upload during lab assessment 3.

Windows will keep all files in the recycle bin indefinitely. However, it is a good practice to clear the recycle bin once and a while. If these files are truly no longer needed, no need to have them taking up space on your system.

# Part 3: Windows File Extensions

A file extension is a way for both the user and the operating system to identify the type of data that is contained in the file. This helps determine which application to opens the file or if it is a system file. You may be familiar with some of the commonly used file extensions:

* .docx – Microsoft Word file
* .xlsx – Microsoft Excel file
* .ppt – Power Point file
* .pdf – Adobe PDF file
* .exe – Executable application file

And many more!

In the previous section, we create three different types of files:

Text Document

Rich Text Document

Bitmap Image

Each of these have different file extensions, but by default Windows hides these.

* Navigate to and open the **PartyPlanning** folder.
* Click on the **View** menu in **File Explorer**.
* Find the check box for **File** name extensions and click it.

![](data:image/png;base64...)

Now the file extensions are visible with the file names.

![](data:image/png;base64...)

* The Text Documents use the file extension .txt
* The Rich Text Document uses the file extension .rtf
* And the Bitmap image uses the file extension .bmp

If we change the file extension, it will change how the operating system identifies and handles the file.

* Double click the **Gift Ideas.txt** file

Since this is a .txt file it opens in Notepad, windows default text editor.

* Double click the **Guest List.rtf** file.

Rich Text format files cannot be opened with notepad because they have more formatting options. Therefore, this file is opened in WordPad.

* Double click the **Partly Locations.bmp** file.

A bitmap is an image (picture) file, so it opens in Microsoft Paint.

* Rename the **Gift Ideas.txt** file to **Gift Ideas.html**
* Click **Yes** to acknowledge the change.

Notice the icon changed for this file. Windows now sees this as an html file, which is a web site file.

* Double click the file now.

Since Windows sees this as a web site file, it tries to open it up in Internet Explorer.


