**Linux Processes**
==================

When we run software on our system or execute a command, processes and services are created. To be an effective systems administrator, we must understand how to identify what is running on our system, determine if they are running properly, and if they should be running at all.

Processes and services that are running improperly could cause issues with system performance. Processes that are running that are not needed increase the attack surface of the system, potentially creating vulnerabilities. Knowing what processes should be running can help you identify malicious software that might have infected the system.

**What is a Process?**
--------------------

A process is a piece of code that has been created or executed by an application or command, such as launching a web browser like Firefox. When a process first starts, it is known as a Foreground Process by default. When a process is in the foreground, it can receive input from the user (such as entering information on the keyboard) and display output to the user (such as displaying text or images on the screen).

**Process States**
-----------------

Processes have four different states that change according to its circumstances:

* **Running**: The process is either currently running in the CPU or is ready to run (waiting to be assigned CPU resources). This is usually the state of a Foreground process.
* **Waiting**: The process is waiting for an event or for a resource. This is usually the state of a Background Process.
* **Stopped**: The process has been stopped by receiving a signal from the user or the system. A stopped process can be used for debugging issues.
* **Zombie**: The process has halted for some unknown reason. The process is dead. This usually indicates an issue.

**Monitoring Processes**
-------------------------

There are many tools that can be used to monitor processes. Two of the most popular that can be found on most Linux systems are `ps` and `top`.

### Using `ps`
-------------

The `ps` (Process Status) command displays a snapshot of all the running processes at a moment in time.

* Run the following command: `ps aux | less`

This output is a list of every process currently running at a moment the command was executed, sorted by the order in which they were started. At the top of the screen, you see the output is broken down into columns:

| USER | PID | %CPU | %MEM | VSZ | RSS | TTY | START | TIME | COMMAND |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

Using `top`
------------

The `top` command displays the top 20 processes running on the system and is updated every couple of seconds. By default, it sorts the processes by CPU percent.

* Run the following command: `Top`

At the top of the tool, you will see the overall status for the system processes, including information such as total process running, sleeping, stopped, or in a zombie state. It also displays system metrics such as overall CPU usage and memory usage.

**Sorting Processes**
----------------------

You can change the order in which the processes are sorted with a few simple keyboard commands:

* Shift+M to sort by memory usage
* Shift+P to sort by CPU usage
* Shift+N to sort by Process ID
* Shift+T to sort by running time

**Killing Processes**
---------------------

When killing a process, we must specify the PID of the process instead of the process name.

* Run the following command: `kill SIGTERM YourPIDHere`

You can also kill processes from within top as well.