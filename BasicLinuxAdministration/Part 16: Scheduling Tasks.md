**Scheduling Tasks**
=====================

Sometimes we may need to run a process repeatedly or on a regular schedule. Perhaps we want to run backups every hour, troubleshoot a network issue, or perhaps just create our own log files to monitor something on our system.

Manually doing these repetitive tasks can take away valuable time from other work, lead to mistakes, and just be incredibly boring. A good systems administrator will find ways to automate these types of tasks. There are many different tools that can help with automation, but the two most basic tools that are free and easy to use are scripts and cronjobs.

**Scripting**
------------

Writing out a series of commands repeatedly is very tedious. Scripting is a way for us to create a simple “program” using the command line that allows us to save that same series of commands. At the most basic level, a script is nothing more than a text file that contains a list of commands.

For an example, we will create a simple script that will monitor established connections to our server and create a log file with time stamps. To do this, we use a couple new commands, `netstat` and `date`.

The `netstat` command displays network connections to our system.
* Run the following command: `netstat -t`

This screen shot shows the results you should see.

Now we need to enter this command into a text file and change the permissions to be executable.
* Open a new text file with vi called “connections.sh”
vi connections.sh
* Add the text as follows and save the file:




#!/bin/bash
netstat -t | grep ESTABLISHED
netstat -t | grep TIME_WAIT
Date >> connections.log
netstat -t | grep ESTABLISHED >> connections.log
netstat -t | grep TIME_WAIT >> connections.log




Next, we must change the permissions so the text file is executable.
* Run the command: `chmod 755 connections.sh`

Now, let’s test out our new script. In order to execute a script, you must enter the full path to the file or specify “./” for the relative path.
* Enter the following into the command prompt:




./connections.sh




You should see similar results as when you ran the `netstat` command itself.

**Cron**
------

Cron is a utility built into the Linux system that allows us to schedule jobs (commands or scripts) to run on a periodic schedule. These tasks are commonly referred to as “cron jobs”. Cron jobs are scheduled in the crontab (cron table), which is a text configuration file used to store multiple instructions.

Before setting up cron jobs, we must first understand the format of the crontab file. The crontab file is laid out like a table, with 7 different columns each separated by a space and a row for each instruction.

The following shows an example of the job definition format:




Column 1 – This defines the minute of the hour to execute the job, from 0-59
Column 2 – This defines the hour of the day to execute the job, from 0-23
Column 3 – This defines the day of the month to execute the job, from 1-31
Column 4 – This defines the month in which to execute the job, from 1-12
Column 5 – This defines the day of the week to execute the job, from 0-7 (Sundays can be 0 or 7)
Column 6 – This is the user in which to run the job as. If left blank, it will be the user that
Column 7 – This is the command or path to the script to be executed.




When setting the schedule, if a column is not needed, simply enter an Asterix (*) for the column.

To edit the crontab file, we will use the command `crontab`. This will open the file in the vi text editor. Specifying the `-e` option will open the current crontab for the logged in user.
* Open the crontab with the following command: `crontab -e`

Let’s go ahead and create a cronjob that will run our script every hour during the month of May.
* Edit the file with the following schedule on the first line:




0 * * 5 * student /home/student/connections




In this example, the first `0` means the job will run at the top of every hour. Since it will run every hour, we used the `*` for the second column. Since it will run every day, we used the `*` for the third column. In the fourth column, since we specified the number 5, it will only run in the 5th month of May.

The fifth column once again has an `*` since it will run every day, regardless of which day it is. We specified the user name but could have left this blank. Sometimes you may need to run a job as a root user. Finally, the last column is the absolute path of the script. If you do not specify the full path, the job will not run.

* Create two new jobs that will run the script according to the following schedules:
	+ Every Saturday morning at 5am
	+ Every 15 minutes, between 8am-5pm, Monday-Friday, during this month