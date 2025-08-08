**Part 7: Working with Text Files**
=====================================

### Reading Text Files
--------------------

Linux relies heavily on simple text files, which are controlled by configuration files, user database files, logs, and many other important functions of the operating system.

* `less` command outputs the text in a file in a page-by-page format.



bash
￼



sudo less /var/log/messages




* Use up/down arrow keys to scroll one line at a time or use "page up" and "page down" keys to scroll between pages. Hit "q" to quit.

* `head` command displays the first 10 lines of a file:



bash
￼



sudo head /var/log/messages




* `tail` command displays the last 10 lines of a file, or use `-f` option for follow mode (display new lines as they are created):



bash
￼



sudo tail -f /var/log/messages





Editing Text Files
------------------

Being able to edit text configuration files from the command line is an essential skill.

* `vi` editor:



bash
￼



sudo vi /home/student/.bashrc




or

* `nano` editor:



bash
￼



sudo nano /home/student/.bashrc




* Move around the file using arrow keys.
* Hit "i" to enter INSERT mode, then make edits. Hit ESC to exit INSERT mode.

To save and quit:

1. Switch to command mode by hitting SHIFT+:.
2. Type `wq` (write + quit) or `q!` (quit without saving).

Let's create an alias:



bash
￼



alias log="sudo tail -f /var/log/messages"




* Hit ESC, then type "wq" and hit Enter to save the file.

Test out your new alias: `log`

**Take a screenshot of running the "log" command**

Note:

1. The three essential commands for using `vi` are:
	+ "I" (Insert Mode)
	+ Shift+: (Command Mode)
	+ wq (Write + Quit) or q! (Quit without saving)

2. For now, you only need to know these basic operations in `vi`.