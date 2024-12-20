

**Introduction to Cryptography**

**Lab 0: Introduction**

**Description:**

There are five cryptography labs. Each lab is designed to accompany one of the chapters in the [Introduction to Ciphers and Cryptography](https://docs.google.com/document/d/1WwEBMd4InZCUgNb4f1QLw2kGBLzApOZK8LCf4Fg3eQo/edit?usp=sharing) text:

* [Lab 1: AES Symmetric Encryption](https://docs.google.com/document/d/1-aLo5mEwVxmy7ejz5ImZyd_7QDUZahC5BqOWe7O3h_0/edit?usp=sharing)
* [Lab 2: RSA Asymmetric Encryption](https://docs.google.com/document/d/1_XG5p9vA73qprylQyHC0h02eoyhua_83y6yMTQ_maZs/edit?usp=sharing)
* [Lab 3: Message Digests](https://docs.google.com/document/d/1W7D-7iTeJBsdyn4q6bVHDtgCve7mxOEPKwgQDuwa-XU/edit?usp=sharing)
* [Lab 4: RSA Authentication](https://docs.google.com/document/d/1m9eIJn5QCLf2-XhA4XlvDaYlLRJe0JrzZfHhbgtF61A/edit?usp=sharing)
* [Lab 5: Digital Certificates](https://docs.google.com/document/d/17JlWP0YMc4EF05DA5UfkJbIoc_YF_hG5UdC2t6xy8uI/edit?usp=sharing)

The labs are designed to be completed using a CentOS Linux virtual machine through the [Ohio Cyber Range Institute](https://www.ohiocyberrangeinstitute.org/) (OCRI).

If you are an educator in Ohio, the OCRI is a free resource available for you to use with your students, and there is a specific VM that you can have loaded to accompany these learning materials. The labs use OpenSSL, and much of the content of the labs could be replicated on any machine running OpenSSL.

**The goals of these labs are to:**

1. Familiarize students with a Linux command line environment
2. Familiarize students with the OpenSSL toolkit
3. Teach students where to find documentation for OpenSSL commands
4. Provide hands-on activities where students apply the concepts from the chapters of the accompanying text to help students better understand cryptography and public key infrastructure (PKI).

**Some Notes to the Student:**

If you have never used a Linux operating system before or never used a command line environment before, it may take a while for you to feel comfortable in this text-based computing environment.

I offer a few hints and tips to help you:

* Linux is case sensitive: Pay careful attention to when a command is lowercase or uppercase. Typing “Cd” instead of “cd” will generate an error.
* Spelling is important: Commands need to be typed exactly as they appear in the labs. Any misspelling will likely generate an error (or have an unintended consequence).
* If you encounter an error, go back over what you typed carefully comparing it to the lab instructions looking for capitalization and spelling errors; these are the most common.
* Syntax matters: Syntax is the order in which phrases or “arguments” appear in the command; don’t mix things up.
* When you type a command and press the Enter key, there is no “success” message or indicator that anything happened. Sometimes students think this means that the command didn’t do anything, but that is actually usually a good sign. If you have made a mistake, then you will get an error message. If you don’t get an error message, then you probably did it right!

**A Few Commands to Get You Started (For New Linux Users):**

If you have little or no experience working in a Linux environment, here are some common commands that will help you get started.

When you first open a new terminal window, you’ll be greeted by a mostly blank screen with something called a command prompt. It will look something like this:

![](data:image/png;base64...)

The **~** indicates that you are in your user’s “home” directory. Every user has a home directory, and you can always return to your home directory using the command **cd ~**.

**Here are some other commands that you may find helpful:**

**pwd** - this stands for print working directory and will give you a full path from the root directory (represented by a forward slash “/”) to your current (or “working”) directory

**cd** - this stands for change directory and you have to specify a directory to change to.

For example, if you are in your home directory, you can type **cd Documents** to change your working directory to the /home/user/Documents directory.

No matter where you are in the file system, you can always go “up” one directory (or “back”) by typing **cd ..** (You must have a space in there)

**ls** - this is short for “list” and will generate a list of the files and directories inside your working directory. Linux commands have “options” that are like accessories that you can add on to the command to adjust how it operates.

If you type **ls -l** (or **ll**) then you will get what is called a “long list” of the contents of your working directory. Try both to compare the difference in the output.

**cat** - is short for “concatenate” which merges two files, but if you just give it one file, then it will simply print the contents of the file to the screen.

So, if you have a file message.txt and you type **cat message.txt**, then you will see the contents of the file on the screen. This is an easy way to read the contents of files.

The file “**message.txt**” is called an “**argument**”. Some commands need an argument to work, others do not. Typically, the argument is the thing that the command is “acting on”.

**echo** - this is a command that will print out text to the screen. For example, **echo “Hello!”** will print Hello! to the screen.

**>>** - this is called a redirection command; it will take whatever is to the left of the **>>** and append it to the stuff to the right of the **>>**.

For example, if you have a file called message.txt and you’d like to add a date stamp to the file you can type **date >>** **message.txt** and the date (and time) will be added to the bottom of the file.

Make sure to use **>>** and NOT > when adding extra information, because a single > will \*overwrite\* the previous contents of the file.

**man** - this is short for manual

Linux is pre-loaded with manual entries for most commands and if you want to find out more about how a command works, what options are available for the command, or what the proper syntax is, you can type **man command** to find out more.

For example, if you wanted to learn more about the ls command you could type **man ls** and you would see that there are a lot of options I did not discuss.

Learning to read the manual documentation for commands is an important Linux skill that will help you grow as you learn more and want to do more and use new commands!

**One final comment on Linux commands:**

Commands follow a general structure:

**command -option1 [-option2] argument1 [argument2]**

**command** - this is the command itself like **cat** or **cd**

**-option1** - options are preceded by a dash and are (as the name implies) optional. In documentation they are shown with the square brackets as I did with [**-option2**] to indicate that they are not required.

**argument1** - this is the input to the command or the file/directory that the command should act on; some commands take no argument, some take one, while others take 2 or more (which is why I put the second argument in square brackets). Some commands have a default argument if you don’t put one in.

**Example:**

**ls** : this will list just the files/directories in the working directory

**ls -l -a** : this will list all the files/directories in the working directory, including the hidden ones (this is the -a option) in “long format” which includes permissions, owners, size, etc. (this is the -l option)

**ls /etc** : this will list the files/directories in the /etc directory (which holds configuration files) no matter what your working directory is when you run it. “/etc” is an example of an argument, but note that the argument is optional. Without it, the default argument is the working directory.

**ls -l -a /etc** : this will list all the files/directories in the /etc directory (no matter what directory you are in when you type it), including the hidden ones (this is the -a option) in “long format” which includes permissions, owners, size, etc. (this is the -l option); here we have an example that uses two options and an argument.


