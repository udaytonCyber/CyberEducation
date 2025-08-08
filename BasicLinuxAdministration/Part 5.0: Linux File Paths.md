**Linux File Paths**
-------------------

### Introduction:

* Each file has a specific file path that specifies where exactly to find the file in the filesystem.
* The file path is made up of all directories above the file, all the way up to the root (/) of the file system.

Types of File Paths:
--------------------

1. **Absolute Path**: Begins at the root of the filesystem (/) and includes all parent directories that the file resides in.
	+ Example: `/home/user/Documents` (where 'user' represents a username)
2. **Relative Path**: Starts from the present working directory (the directory the command prompt is currently pointing to).
	+ Example: `./Documents`

Using Absolute Paths:
----------------------

* Always specify the correct path to a file when working with them.
* Avoid using relative paths if you're not sure where your current working directory is.

Using Relative Paths:
---------------------

1. Determine the present working directory by running the command `pwd`.
2. Use the relative format for the path, starting from the present working directory (e.g., `./Documents`).
3. Be careful when using relative paths; make sure you're in the correct directory to avoid mistakes.

Example: Bob's Party Planning File
--------------------------------

* Bob creates a file called "PartyPlanning.txt" and uses the relative path `./Documents/PartyPlanning.txt`.
* If Alice logs out, but Bob doesn't realize it, the present working directory becomes `/home/Alice/`, and the file is created in her home directory instead of his.
* Using an Absolute Path (e.g., `/home/Bob/Documents/PartyPlanning.txt`) would have avoided this mistake.

Conclusion:
----------

1. Always specify the correct path to a file when working with them.
2. Use Absolute Paths while getting used to the Linux command line; it may take more time, but it will save you from making mistakes.
3. Be careful when using Relative Paths and make sure you're in the correct directory to avoid errors.