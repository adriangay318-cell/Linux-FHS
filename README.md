# Linux-FHS
This includes commands, flags, FHSs, and more.
## Need folders & subfolders in '/':
 / (Root)
├── bin (Essential Binaries: ls, cp, bash)
├── boot (Static Boot Files: Kernel, Grub)
├── dev (Device Files: sda1, tty, random)
├── etc (System Configurations: passwd, fstab)
├── home (User Home Directories: /home/alice)
├── lib (Shared Libraries for /bin and /sbin)
├── media (Removable Media: USB sticks, CD-ROMs)
├── mnt (Temporary Mount Points)
├── opt (Optional Third-Party Software)
├── proc (Process Information: Virtual Filesystem)
├── root (Home Directory for the Root User)
├── run (Runtime Data: PIDs, Sockets)
├── sbin (System Admin Binaries: fdisk, iptables)
├── tmp (Temporary Files)
├── usr (User System Resources)
└── var (Variable Data: Logs, Spools, Caches)

### usr FHS:
  usr (User System Resources)
    ┃
    ┣━━ bin/        (Standard user commands: python, git, wget)
    ┃
    ┣━━ sbin/       (Non-essential system admin binaries)
    ┃
    ┣━━ lib/        (Libraries for binaries in /usr/bin and /usr/sbin)
    ┃
    ┣━━ local/      (The "Admin's Territory" - for manual installs)
    ┃   ┣━━ bin/    (Locally compiled programs)
    ┃   ┗━━ lib/    (Local libraries)
    ┃
    ┣━━ share/      (Architecture-independent data)
    ┃   ┣━━ man/    (Manual pages)
    ┃   ┣━━ doc/    (Miscellaneous documentation)
    ┃   ┗━━ icons/  (System-wide icons and themes)
    ┃
    ┣━━ include/    (C/C++ header files for development)
    ┃
    ┗━━ src/        (Kernel source code or system source files)
### var FHS:
var (Variable Data)
┃
┣━━ cache/ (Data locally generated to speed up programs)
┃ ┣━━ apt/ (Package manager cache)
┃ ┗━━ man/ (Pre-formatted manual pages)
┃
┣━━ lib/ (Persistent state information)
┃ ┣━━ mysql/ (Database storage)
┃ ┣━━ docker/ (Container images and data)
┃ ┗━━ dpkg/ (Package management status)
┃
┣━━ log/ (System and Application Logs)
┃ ┣━━ syslog (Central system log)
┃ ┣━━ auth.log (Security and login logs)
┃ ┗━━ apache2/ (Web server access/error logs)
┃
┣━━ mail/ (User mailbox files)
┃
┣━━ opt/ (Variable data for /opt packages)
┃
┣━━ run/ (Runtime data: PIDs, sockets - linked to /run)
┃
┣━━ spool/ (Data waiting to be processed)
┃ ┣━━ cron/ (Scheduled system tasks)
┃ ┣━━ cups/ (Printer queues)
┃ ┗━━ mail/ (Outgoing mail queue)
┃
┣━━ tmp/ (Temporary files preserved between reboots)
┃
┗━━ www/ (Standard location for Web Server files)*
*Common convention, though not strictly FHS required.
## About var:
+ The "Big Three": Most of your disk space issues will happen in `/var/log`, `/var/lib`, or `/var/cache`.
+ Cleaning Logs: You can check which log is eating space using `du -sh /var/log/* | sort -h`.
+ Database Moves: If your database in `/var/lib` gets too big, admins often move it to a larger drive and "symlink" it back.
### About / (root):
 Every system has a root (/), and you can't make another one, to fix that you would rename / to sysroot or root and then the Computer will turn it into /.
  
## Commands:
+ cat: Utility to concatenate files to standard output
+ chgrp: Utility to change file group ownership
+ chmod: Utility to change file access permissions
+ chown: Utility to change file owner and group
+ cp: Utility to copy files and directories
+ date: Utility to print or set the system data and time
+ dd: Utility to convert and copy a file
+ df: Utility to report filesystem disk space usage
+ dmesg: Utility to print or control the kernel message buffer
+ echo: Utility to display a line of text
+ false: Utility to do nothing, unsuccessfully
+ hostname: Utility to show or set the system's host name
+ kill: Utility to send signals to processes
+ ln: Utility to make links between files
+ login: Utility to begin a session on the system
+ ls: Utility to list directory contents
+ mkdir: Utility to make directories
+ mknod: Utility to make block or character special files
+ more: Utility to page through text
+ mount: Utility to mount a filesystem
+ mv: Utility to move/rename files
+ ps: Utility to report process status
+ pwd: Utility to print name of current working directory
+ rm: Utility to remove files or directories
+ rmdir: Utility to remove empty directories
+ sed: The `sed' stream editor
+ sh: POSIX compatible command shell
+ stty: Utility to change and print terminal line settings
+ su: Utility to change user ID
+ sync: Utility to flush filesystem buffers
+ true: Utility to do nothing, successfully
+ umount: Utility to unmount file systems
+ uname: Utility to print system information
