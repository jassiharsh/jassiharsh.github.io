---
layout: post
title:  "Linux Command Line Cheatsheet"
date:   2020-07-28 21:03:36 +0530
categories: Linux
---


Useful Linux Command Line cheatsheet.

# Topics
---
1. [System Information](#system-information)
2. [Directory Navigation](#directory-navigation)
3. [File and Directory Commands](#file-and-directory-commands)
4. [Search](#search)
5. [SSH Logins](#ssh-logins)
6. [File Permissions](#file-permissions)
7. [File Transfers](#file-transfers)
8. [Archives tar file](#archives-tar-file)
9. [Disk Usage](#disk-usage)
10. [Process Management](#process-management) 

## System Information
---
### Display Linux system information
`uname -a`

### Display kernel release information
`uname -r`

### Show which version of redhat installed
`cat /etc/redhat-release`

### Show how long the system has been running + load
`uptime`

### Show system host name
`hostname`

### Display the IP addresses of the host
`hostname -I`

### Show system reboot history
`last reboot`

### Show the current date and time
`date`

### Show this month's calendar
`cal`

### Display who is online
`w`

### Who you are logged in as
`whoami`

## Directory Navigation
---
### To go up one level of the directory tree.  (Change into the parent directory.)
`cd ..`

### Go to the $HOME directory
`cd`

### Change to the /etc directory
`cd /etc`


## File and Directory Commands
---
### List all files in a long listing (detailed) format
`ls -al`

### Display the present working directory
`pwd`

### Create a directory
`mkdir directory`

### Remove (delete) file
`rm file`

### Remove the directory and its contents recursively
`rm -r directory`

### Force removal of file without prompting for confirmation
`rm -f file`

### Forcefully remove directory recursively
`rm -rf directory`

### Copy file1 to file2
`cp file1 file2`

### Copy source_directory recursively to destination. If destination exists, copy source_directory into destination, otherwise create destination with the contents of source_directory.
`cp -r source_directory destination`

### Rename or move file1 to file2. If file2 is an existing directory, move file1 into directory file2
`mv file1 file2`

### Create symbolic link to linkname
`ln -s /path/to/file linkname`

### Create an empty file or update the access and modification times of file.
`touch file`

### View the contents of file
`cat file`

### Browse through a text file
`less file`

### Display the first 10 lines of file
`head file`

### Display the last 10 lines of file
`tail file`

### Display the last 10 lines of file and "follow" the file as it grows.
`tail -f file`

## Search
---
### Search for pattern in file
`grep pattern file`

### Search recursively for pattern in directory
`grep -r pattern directory`

### Find files and directories by name
`locate name`

### Find files in /home/john that start with "prefix".
`find /home/john -name 'prefix*'`

### Find files larger than 100MB in /home
`find /home -size +100M`

## SSH Logins
---
### Connect to host as your local username.
`ssh host`

### Connect to host as user
`ssh user@host`

### Connect to host using port
`ssh -p port user@host`

## File Permissions
---
![linux-permissions-chart](https://raw.githubusercontent.com/jassiharsh/jassiharsh.github.io/master/imgs/linux-permissions-chart.png)

        PERMISSION      EXAMPLE

         U   G   W
        rwx rwx rwx     chmod 777 filename
        rwx rwx r-x     chmod 775 filename
        rwx r-x r-x     chmod 755 filename
        rw- rw- r--     chmod 664 filename
        rw- r-- r--     chmod 644 filename

### NOTE: Use 777 sparingly!

        LEGEND
        U = User
        G = Group
        W = World

        r = Read
        w = write
        x = execute
        - = no access

## File Transfers
---
### Secure copy file.txt to the /tmp folder on server
`scp file.txt server:/tmp`

### Copy *.html files from server to the local /tmp folder.
`scp server:/var/www/*.html /tmp`

### Copy all files and directories recursively from server to the current system's /tmp folder.
`scp -r server:/var/www /tmp`

### Synchronize /home to /backups/home
`rsync -a /home /backups/`

### Synchronize files/directories between the local and remote system with compression enabled
`rsync -avz /home server:/backups/`

## Archives tar file
---
### Create tar named archive.tar containing directory.
`tar cf archive.tar directory`

### Extract the contents from archive.tar.
`tar xf archive.tar`

### Create a gzip compressed tar file name archive.tar.gz.
`tar czf archive.tar.gz directory`

### Extract a gzip compressed tar file.
`tar xzf archive.tar.gz`

### Create a tar file with bzip2 compression
`tar cjf archive.tar.bz2 directory`

### Extract a bzip2 compressed tar file.
`tar xjf archive.tar.bz2`

## Disk Usage
---
### Show free and used space on mounted filesystems
`df -h`

### Show free and used inodes on mounted filesystems
`df -i`

### Display disks partitions sizes and types
`fdisk -l`

### Display disk usage for all files and directories in human readable format
`du -ah`

### Display total disk usage off the current directory
`du -sh`

## Process Management
---
### Display your currently running processes
`ps`

### Display all the currently running processes on the system.
`ps -ef`

### Display process information for processname
`ps -ef | grep processname`

### Display and manage the top processes
`top`

### Interactive process viewer (top alternative)
`htop`

### Kill process with process ID of pid
`kill pid`

### Kill all processes named processname
`killall processname`

### Start program in the background
`program &`

### Display stopped or background jobs
`bg`

### Brings the most recent background job to foreground
`fg`

### Brings job n to the foreground
`fg n`
