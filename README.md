# UNIX/Linux operating systems (Basic).

Linux system installation and updates. Administration basics.

## Contents

1. [Chapter I](#chapter-i)
2. [Chapter II](#chapter-ii) \
   2.1. [Linux](#linux)  
   2.2. [Administration](#administration)  
   2.3. [Virtual machines](#virtual-machines)
3. [Chapter III](#chapter-iii) \
   3.1 [Installation of the OS](#part-1-installation-of-the-os)  
   3.2 [Creating a user](#part-2-creating-a-user)  
   3.3 [Setting up the OS network](#part-3-setting-up-the-os-network)   
   3.4 [OS Update](#part-4-os-update)  
   3.5 [Using the sudo command](#part-5-using-the-sudo-command)  
   3.6 [Installing and configuring the time service](#part-6-installing-and-configuring-the-time-service)  
   3.7 [Installing and using text editors](#part-7-installing-and-using-text-editors)  
   3.8 [Installing and basic setup of SSHD service](#part-8-installing-and-basic-setup-of-the-sshd-service)  
   3.9 [Installing and using the top, htop utilities](#part-9-installing-and-using-the-top-htop-utilities)   
   3.10 [Using the fdisk utility](#part-10-using-the-fdisk-utility)   
   3.11 [Using the df utility](#part-11-using-the-df-utility)    
   3.12 [Using the du utility](#part-12-using-the-du-utility)    
   3.13 [Installing and using the ncdu utility](#part-13-installing-and-using-the-ncdu-utility)    
   3.14 [Working with system logs](#part-14-working-with-system-logs)     
   3.15 [Using the CRON job scheduler](#part-15-using-the-cron-job-scheduler)


## Part 1. Installation of the OS

**== Task ==**

##### Install **Ubuntu 20.04 Server LTS** without GUI. (Use VirtualBox).


## Part 2. Creating a user

**== Task ==**

##### Create a user other than the one created during installation. The user must have permission to read logs from the /var/log folder.

## Part 3. Setting up the OS network

**== Task ==**

##### Set the machine name as user-1
##### Set the time zone corresponding to your current location.

##### Output the names of the network interfaces using a console command.
- In the report give an explanation for the presence of the lo interface.
##### Use the console command to get the ip address of the device you are working on from the DHCP server.
- Decode DHCP in the report.
##### Define and display the external ip address of the gateway (ip) and the internal IP address of the gateway, aka default ip address (gw).
##### Set static (manually set, not received from DHCP server) ip, gw, dns settings (use public DNS servers, e.g. 1.1.1.1 or 8.8.8.8).

##### Reboot the virtual machine. Make sure that the static network settings (ip, gw, dns) correspond to those set in the previous point.
- Describe in the report what you have done to complete all seven points (you can do it in text or with screenshots).
- Successfully ping 1.1.1.1 and ya.ru remote hosts and add a screenshot of the output command to the report.

## Part 4. OS Update

**== Task ==**

##### Update the system packages to the latest version
- After updating the system packages, if you enter the update command again, a message should appear saying there are no updates.
- Add a screenshot of this message to the report.

## Part 5. Using the **sudo** command

**== Task ==**

##### Allow user created in [Part 2](#part-2-creating-a-user) to execute sudo command.
- In the report explain the *true* purpose of sudo command 
- Change the OS hostname via the user created in [Part 2](#part-2-creating-a-user) (using sudo).
- Add screenshot with changed hostname to the report.

## Part 6. Installing and configuring the time service

**== Task ==**

##### Set up the automatic time synchronisation service.
- Output the time of the time zone in which you are currently located.
- The output of the following command must contain `NTPSynchronized=yes`: \
  `timedatectl show`
- Add screenshots of the correct time and command output to the report.

## Part 7. Installing and using text editors

**== Task ==**

##### Install **VIM** text editor (+ any two others if you like **NANO**, **MCEDIT**, **JOE** etc.)

##### Using each of the three selected editors, create a *test_X.txt* file, where X is the name of the editor in which the file is created. Write your nickname in it, close the file and save the changes.
- Add screenshots to the report:
    - Of each editor with the contents of the file before closing.
- Write down in the report what you have done to exit with the changes saved.

##### Using each of the three selected editors, open the file for editing, edit the file by replacing the nickname with the "21 School 21" string, close the file without saving the changes.
- Add screenshots to the report:
    - Of each editor with the contents of the file after editing.
- Write down in the report what you have done to exit without saving the changes.
##### Using each of the three selected editors, edit the file again (similar to the previous point) and then master the functions of searching through the contents of a file (a word) and replacing a word with any other one.
- Add screenshots to the report:
    - Of each editor with word search results.
    - Of each editor with commands entered to replace a word with another.

## Part 8. Installing and basic setup of the **SSHD** service

`-` It's convenient to have access from one computer to another over a network, isn't it? But to make it not only convenient, but also safe, you should use SSH service.

**== Task ==**

##### Install the SSHd service.
##### Add an auto-start of the service whenever the system boots.
##### Reset the SSHd service to port 2022.
##### Show the presence of the sshd process using the ps command. To do this, you need to match the keys to the command.
- Explain in the report the meaning of the command and each key in it.
##### Reboot the system.
- Describe in the report what you have done to complete all five points (you can do this in text or with screenshots).
- The output of the netstat -tan command should contain \
  `tcp 0 0.0.0.0:2022 0.0.0.0:* LISTEN` \
  (if there is no netstat command, it needs to be installed)
- Add a screenshot of the command output to the report.
- Explain the meaning of the -tan keys, the value of each output column, the value 0.0.0.0. in the report.

## Part 9. Installing and using the **top**, **htop** utilities

`-` If I were asked what useful things **top** and **htop** utilities do, I would answer in one word: everything.

**== Task ==**

##### Install and run the top and htop utilities.
- From the output of the top command determine and write in the report:
    - uptime
    - number of authorised users
    - total system load
    - total number of processes
    - cpu load
    - memory load
    - pid of the process with the highest memory usage
    - pid of the process taking the most CPU time
- Add a screenshot of the htop command output to the report:
    - sorted by PID, PERCENT_CPU, PERCENT_MEM, TIME
    - filtered for sshd process
    - with the syslog process found by searching
    - with hostname, clock and uptime output added

## Part 10. Using the **fdisk** utility

`-` Now let's figure out how to get information about your hard disk. Especially for you I've put together a couple of examples of how to use the fdisk utility.

**== Task ==**

##### Run the fdisk -l command.
- In the report write the name of the hard disk, its capacity and number of sectors, and also the swap size.

## Part 11. Using the **df** utility

`-` We got the information about the hard disk, but often it is much more interesting to get information about the disk space, which can be obtained with the df utility.

**== Task ==**

##### Run the df command.
- In the report write for the root partition (/):
    - partition size
    - space used
    - space free
    - percentage used
- Determine and write the measurement unit in the report.

##### Run the df -Th command.
- In the report write for the root partition (/):
    - partition size
    - space used
    - space free
    - percentage used
- Determine and write the file system type for the partition in the report.

## Part 12. Using the **du** utility

`-` df is not the only way to get information about disk space. I'll tell you about another one.

**== Task ==**

##### Run the du command.
##### Output the size of the /home, /var, /var/log folders (in bytes, in human readable format)
##### Output the size of all contents in /var/log (not the total, but each nested element using *)
- Add screenshots with the output of all used commands to the report.

## Part 13. Installing and using the **ncdu** utility

`-` You probably didn’t like much the format in which the du command outputs information. I understand you perfectly. So now we'll take a look at its improved version.

**== Task ==**

##### Install the ncdu utility.
##### Output the size of the /home, /var, /var/log folders.
- The size should be approximately the same as in [Part 12](#part-12-using-the-du-utility).

- Add screenshots of the used commands to the report.

## Part 14. Working with system logs

`-` A system administrator sometimes needs to review events which happened in a system in the recent past. Linux has system logs for that.

**== Task ==**

##### Open for viewing:
##### 1. /var/log/dmesg
##### 2. /var/log/syslog
##### 3. /var/log/auth.log
- Write the last successful login time, user name and login method in the report.
- Restart SSHd service.
- Add a screenshot of the service restart message to the report (search for it in the logs).

## Part 15. Using the **CRON** job scheduler

`-` Phew, we finally got to the last part of my long narrative. I will now show you the program, which, among other things, noticeably simplifies the periodic invocation of other programs.

**== Task ==**

##### Using the job scheduler, run the uptime command in every 2 minutes.
- Find lines in the system logs (at least two within a given time range) about the execution.
- Display a list of current jobs for CRON.
- Add screenshots of the execution lines and the list of current tasks to the report.

##### Remove all tasks from the job scheduler.
- Add a screenshot of the list of current tasks for CRON to the report.
