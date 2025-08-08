## Limitations and Advantages of GUIs

While Graphical User Interfaces (GUIs) are very useful and generally intuitive, they do have their limits and downfalls. GUIs are designed to accomplish basic or common tasks, like opening an application. However, many applications have different ways of functioning that are sometimes not programmed into the GUI. This limits the user’s ability to control the system and applications.

GUIs also take a significant amount of resources (CPU time, RAM memory, Hard disk space, etc.) to run, which can hinder the performance of a system, especially with limited resources or demanding tasks running.

GUIs can also make it more challenging to control systems remotely. Sometimes you need special tools or hardware to view a GUI over a network, and using the tools can increase potential security vulnerabilities to the system.

For these reasons and others, many computer experts prefer to use the Command Line Interface (CLI) to control their systems. Linux, in particular, offers a lot of extras when using the CLI.

## Command Line Interface (CLI)

Open the terminal application again. You will be greeted with what is known as a command prompt. There is some very useful information located here.

- The first part of the prompt contains the username that you are currently logged in as, which in this case is `student`.
- After the `@` symbol, there is the computer name or hostname that you are currently logged into.
- The next piece of information shows you what directory you are currently in. Right now, you are in the user’s home directory, indicated by a `~` (tilde).
- The `$` (dollar sign) symbol tells you that you are logged in as a normal user in the Bash Shell (commonly used in Linux). A `#` (hashtag/pound sign) would mean you are logged in as a superuser (administrator).

The last thing you see is the cursor. This is where we can input commands and information into the system.

### Basic Commands

Now let’s learn some basic commands. Note that all commands are case sensitive.

- Enter the command `pwd` and then hit enter to run. This command is known as print working directory. It outputs the path to the current directory you are working in, which in this case is the user’s home directory.
- The next command is `ls`, which lists the contents of the current directory.
- Another very useful command is `man`. For example, entering `man ls` will display the manual or help page for the `ls` command.

Commands can be used with options (also called switches or flags) that change the functionality of the command. For example:

- Enter the command `ls -l` for a long listing that includes file permissions.
- Enter the command `ls -lr` to display the output in reverse order (alphabetically).

Along with options, we can use parameters (or arguments) to input information into the command. For example:

- Enter the command `ls /var` to list the contents of the `/var` directory.
## Using Parameters and Aliases in Linux

By adding the parameter `/var`, we instruct the command to perform a directory listing of the `/var` directory, rather than the current directory.

### Aliases

Commands can also have aliases, which are shortcuts for longer, more complicated commands. Some aliases are built into the system, and we can create our own.

- For example, enter the command `ll`. This command is an alias for `ls -l`.
- To create your own alias, enter `alias var='ls -l /var'`.
- Now, by entering the alias you just created, `var`, you can get a long directory listing of the `/var` directory without typing out the full command.

**Note**: This alias will only last until the terminal application is shut down. We will learn how to make this permanent by editing a configuration file later.

### Redirecting Command Output

Sometimes we want to use the output of a command differently, not just printing it to the screen. There are several operators that allow us to manipulate the output.

#### The Pipe Operator

The pipe (`|`) is a useful operator that allows us to take the output of one command and use it as input for another command. It must be used with two or more commands. For example:

- Enter `ls /bin` to output the directory listing of the `/bin` directory.
- Now, enter `ls /bin | less`. The `less` command allows you to scroll through the information page-by-page.

#### The Redirect Operator

We can also redirect the output of a command to a text file using the `>` operator.

- Enter `ls /bin > dir.txt`. This command redirects the output to a new file called `dir.txt`.
- To view the file, enter `less dir.txt`.

#### Appending to Files

To append information to the end of a file, we use the `>>` operator.

- Enter the following commands:
  - `date >> dir.txt`
  - `ls /etc >> dir.txt`
  - `less dir.txt`

The `>>` operator appends to a file or creates the file if it doesn't exist, while the `>` operator overwrites the file if it exists or creates it if it doesn't.

### Viewing Command History

The `history` command displays a list of all the commands entered during the current terminal session. To reissue a command:

- Use the up and down arrow keys to scroll through the command history.
- To rerun a specific command, type `!` followed by the command number, like `!950`.
- To rerun the last command, use `!!`. For example, `sudo !!` reruns the last command with administrator privileges.


Tab completion is a feature that helps complete long commands or filenames:

- Start typing the command or filename and press the `Tab` key to auto-complete it.
- If multiple files start with the same letters, press `Tab` twice to list them all.

For example:

- Type `D` and hit `Tab` twice to list all files starting with 'D'.
- Type `Doc` and hit `Tab` once to complete it to `Documents`.

This feature works with any directory, file, or command and is a great time-saver.