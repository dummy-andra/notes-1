# Linux+ Guide to Linux Certification 3rd ed., by Jason W. Eckert
##  1 Introduction to Linux
Operating systems
Linux operating system
  - Versions of Linux
  - Identifying kernel versions
  - Licensing Linux
  - Linux advantages
History of Linux
  - UNIX
  - Hacker culture
  - Linux
Linux distributions
Common uses of Linux
  - Internet servers
  - File and print servers
  - Application servers
  - Supercomputers
  - Scientific/engineering workstations
  - Office/personal workstations
##  2 Linux Installation and usage
Installing Linux
  - Preparing for installation
  - Installation methods
  - Performing the installation
Basic Linux usage
  - Shells, terminals, and the kernel
  - Basic shell commands
  - Shell metacharacters
  - Getting command help
  - Shutting down the Linux system
##  3 Exploring Linux filesystems
Linux directory structure
  - Changing directories
Viewing files and directories
  - File types
  - Filenames
  - Listing files
  - Wildcard metacharacters
Displaying the contents of text files
Displaying the contents of binary files
Searching for text within files
  - Regular expressions
  - `grep`
Editing text files
  - `vi` editor
  - Other common text editors
Topics: cat, cd, grep, egrep, fgrep, file, less, ll, ls, more, nano, od, pwd, strings, tac, tail, vi
##  4 Linux filesystem management
Filesystem Hierarchy Standard : /bin, /boot, /dev, /etc, /home, /lib, /media, /mnt, /opt, /proc, /root, /sbin, /tmp, /usr, /usr/local, /var
Managing files and directories
Finding files
Linking files
File and directory permissions
  - File and directory ownership
  - Managing file and directory permissions
  - Default permissions
  - Special permissions
Topics: chgrp, chmod, chown, cp, ln, locate, rm, rmdir, touch, umask
##  5 Linux filesystem administration
/dev directory
Filesystems
  - Filesystem types
  - Mounting
Working with floppy disks
Working with CDs, DVDs, and ISO images
Working with hard disks
  - Standard hard disk partitioning
  - Working with standard hard disk partitions
  - Working with the LVM
Working with USB and FireWire-based storage devices
Monitoring filesystems
Hard disk quotas
Files: /etc/fstab, /etc/mtab, /proc/devices, 
Topics: /dev/MAKEDEV, cfdisk, df, du, edquota, fdisk, fsck, fuser, lvcreate, lvdisplay, lvextend, lvscan, mkfs, mkisofs, mknod, mkswap, mount, pvcreate, pvdisplay, pvscan, quota, quotaoff, quotaon, repquota, swapon, swapoff, tune2fs, umount, vgcreate, vgdisplay, vgextend, vgscan
##  6 Advanced installation
Advanced storage configuration
  - SCSI hard disk configuration
  - RAID configuration
Installation methods
  - CD Installation
  - USB Flash Drive installation
  - Hard disk installation
  - Network-based installation
Automating Linux installations
Troubleshooting installations
  - Problems starting the installation
  - Problems during installation
  - Problems after installation
Topics: dd 
##  7 Working with the bash shell
Command input and output
  - Redirection
  - Pipes
Shell variables
  - Environment variables
  - User-defined variables
  - Other variables
  - Environment files
Shell scripts
Escape sequences
  - Reading standard input
  - Decision constructs
  - Loop constructs
Topics: alias, awk, echo, env, export, grep, read, sed, set, sort, tee, tr
##  8 System initialization and X Windows
Boot process
Boot loaders
  - GRUB
  - LILO
  - Dual booting Linux
Linux initialization
  - Runlevels
  - /etc/inittab file
  - Runtime configuration scripts
  - Configuring daemon startup
X Windows system
  - Linux GUI components
  - Starting and stopping X Windows
Configuring X Windows
Topics: grub-install, grub-md5-crypt, init, lilo, runlevel, service, system-config-display, system-config-keyboard, telinit, .dmrc, .xinitrc, /boot/grub/grub.conf, /etc/inittab, /etc/lilo.conf, /etc/rc.d/rc.local, /etc/rc.d/rc.sysinit, /etc/rc.d/init.d, /etc/rc.d/rc*.d
##  9 Managing Linux processes
Linux processes
Viewing processes
Killing processes
Process execution
Running processes in the background
Process priorities
Scheduling commands
  - Scheduling commands with `atd`
  - Scheduling commands with the `cron` daemon
Topics: at, atd, bg, crontab, fg, jobs, killall, kill, nice, ps, pstree, renice, top, /etc/at.allow, /etc/at.deny, /etc/cron.allow, /etc/cron.d, /etc/cron.deny, /etc/crontab, /var/spool/at, /var/spool/cron
##  10 Common administrative tasks
### 10A 
Printer administration\
### 10A1
Common Unix printing system
### 10A2
Managing print jobs
### 10A3
LPD Printing system
### 10A4
Configuring printers
### 10B 
> Log file administration
Configuration file  | Description
:---                | :---
**/dev/log**            | location of `rsyslogd` socket for other system processes to write to [440]
**/etc/logrotate.conf** | `logrotate` configuration file [445]
**/etc/logrotate.d/**   | `logrotate` configuration files which override those in **/etc/logrotate.conf** [445]
**/etc/rsyslog.conf**   | `rsyslogd` configuration file [440]
**/etc/syslog.conf**    | `syslogd` configuration file on legacy Linux systems [442]
**/var/log**            | typical location of logs recorded by daemons

Information and error messages recorded by daemons are called **log files** and typically stored in `/var/log`
### 10B1 
> System log daemon `rsyslogd`
**System Log Daemon `rsyslogd`** handles the logging of most events in a centralized fashion. Syslog entries have the format `facility.priority` followed by the location of the logfile in which the notifications are to be stored. The **facility** is the area of the system emitting the notification, and **priority** refers to the precedence of the information.\
Logs can also be sent to another computer using the format `facility.priority @host:port`
#### 10B1A
Format of entries in **/etc/rsyslog.conf**
```
facility.priority  /var/log/logfile
```
#### 10B1B
Example syslog entries [443]
```conf
# Listen for kernel messages with a priority of warning and above
kern.warning /var/log/logfile

# Warning messages from the kernel
kern.=warning /var/log/logfile

# Log all kernel messages
kern.* /var/log/logfile

# Specify multiple facilities and priorities using semicolon `;`, log all messages except warnings
kern.*;kern.!=warn /var/log/logfile

# Log all warnings from all facilities except for the kernel, use `none` keyword
*.=warn;kern.none /var/log/logfile
```
#### 10B1C
Sample **/etc/rsyslog.conf** file [440-442]
```conf
#rsyslog v3 config file

# Provide support for local system logging
$ModLoad imuxsock.so

# Provide kernel logging support (previously done by rklogd)
$ModLoadimklog.so

# Provide --MARK-- message capability
$ModLoadimmark.so

# Provide UDP syslog reception
$ModLoad imudp.so
$UDPServerRun 514

# Provide TCP syslog reception
$ModLoad imtcp.so
$Input TCPServerRun 514

# GLOBAL DIRECTIVES #
# Use default timestamp format
$ActionFileDefaultTemplate RSYSLOG_TraditionalFileFormat

# File syncing capability is disabled by default
#$ActionFileEnableSync on

# RULES #
# Log all kernel messages to the console
kern.* /dev/console

# Log anything of level info or higher, but don't log private authentication messages
*.info;mail.none;news.none;authpriv.none;cron.none /var/log/messages

# Log all mail messages in one place
mail.* -/var/log/maillog

# Log cron stuff
cron.* /var/log/cron

# Everybody gets emergency messages
*.emerg *

# Save news errors of level crit and higher in a special file
uucp,news.crit /var/log/spooler

# Save boot messages to boot.log
local7.* /var/log/boot.log

# FORWARDING RULE #
# The following block of statements define a single forwarding rule and belong together

# Where to place spool files
$WorkDirectory /var/spppl/rsyslog

# Unique name prefix for spool files
$ActionQueueFileName fwdRule1

# 1GB space limit
$ActionQueueMaxDiskSpace 1g

# Save messages to disk on shutdown
$ActionQueueSaveOnShutdown on

# Run asynchronously
$ActionQueueType LinkedList

# Infinite retries if host is down
$ActionResumeRetryCount -1

# Remote host is in the format `ip:port` e.g. 192.168.0.1:514
*.* @@remote-host:514

# INN
news.=crit /var/log/news/news.crit
news.=err /var/log/news/news.err
news.notice /var/log/news/news.notice
news.=debug /var/log/news/news.debug
```
### 10B2
Manually clear log files or use `logrotate` to back them up. `logrotate` will rename log files on a cyclic basis, and a specific number of backups to keep can be set. `logrotate` is typically scheduled to run daily via a cronjob.
#### 10B2A
Manually run logrotate
```sh
logrotate /etc/logrotate.conf
```
#### 10B2B
Example **/etc/logrotate.conf** file
```conf
# Rotate log files weekly
weekly

# Keep 4 weeks of backups
rotate 4

# Create new (empty) log files after rotating old ones
create

# Use date as a suffix of the rotated file
dateext

# Compress logs
compress

# RPM packages drop log rotation information into this directory
include /etc/logrotate.d

# No packages own wtmp and btmp, they are rotated here. wtmp is rotated monthly, only if the size of the log is at least 1 MB. The new log file has the permissions 664 with the owner root and group uttmp. For btmp, the rotation is monthly, and no errors are reported if the log is missing.
/var/log/wtmp {
  monthly
  create 0664 root uttmp
  minsize 1M
  rotate 1 }
/var/log/btmp {
  missingok
  monthly
  create 0600 root utmp
  rotate 1 }
```
### 10C
Administering users and groups\

### Administering users and groups
#### Creating user accounts
#### Modifying user accounts
#### Deleting user accounts
#### Managing groups
Topics: cancel, chage, chfn, chsh, cupsaccept, cupsd, cupsdisable, cupsenable, cupsreject, groupadd, groupdel, groupmod, groups, id, logrotate, lpadmin, lpc, lp, lpq, lpr, lprm, lpstat, newgrp, passwd, pwconv, pwunconv, useradd, userdel, usermod, /etc/cups/cupsd.conf, /etc/cups/printers.conf, /etc/default/useradd, /etc/group, /etc/login.defs, /etc/logrotate.conf, /etc/passwd, /etc/shadow, /etc/skel, /etc/syslog.conf, /var/log 

## 11 Compression, system backup, and software installation
### File compression
`compress` : one of the oldest compression tools available to Unix-like systems, uses Adaptive Lempel-Ziv (LZW) coding with an average compression ratio of 40-50%, appends ".Z" to filenames of inputfiles
`compress -v file1 file2`
`zcat` : display contents of files compressed with `compress` or `gzip` (also `zmore`, `zless`)
`uncompress` : decompress files compressed with `compressed`
`gzip` : utility that uses Lempel-Ziv compression algorithm (LZ77) with an average compression ratio of 60-70%, appends ".gz" filename extension
`gzip -d archive` : decompress {archive} (same as `gunzip archive`)
`bzip2` :  utility that uses Burrows-Wheeler Block Sorting Huffman Coding algorithm, with an average compression ratio of 50-75% (`zcat`, `zmore`, and `zless` cannot be used with compressed archives), with a default filename extension of ".bz2"
`bzcat` : display contents of bz2 files (also `bzmore`, `bzless`)
`bunzip2`
### System backup
`tar` : one of the oldest backup utilities
  - `cpio` utility
  - `dump`/`restore` utility
  - Burning software
### Software installation
  - Compiling source code into programs
  - Installing programs using RPM: `rpm` and `yum` package management tools (dpkg and apt are only tangentially covered in a single Note)
Topics: *sum (sha1sum, etc), bunzip2, bzcat, bzip2, bzless, bzmore, compress, cpio, dump, gcc, gzip, gunzip, restore, rpm, tar, uncompress, yum, zcat, zless, zmore, /etc/dumpdates

## 12 Network configuration
Networks
TCP/IP protocol
  - IPv4 protocol
  - IPv6 protocol
Configuring a network interface
Configuring a PPP interface
Name resolution
Routing
Network services
Remote administration
  - Telnet
  - Remote commands
  - Secure shell (ssh)
  - Remote X Windows
  - Virtual Network Computing (VNC)
Topics: hostname, ifconfig, insmod, ip, lsmod, modprobe, ping, rsh, rlogin, rcp, rmmod, route, ssh, telnet, traceroute, vncpasswd, vncviewer, whois

## 13 Configuring network services
Infrastructure services
  - DHCP
  - DNS
  - NTP
  - NIS
Web services
File sharing services
  - Samba
  - NFS
  - FTP
E-mail services
  - Working with `sendmail`
  - Working with `postfix`
Database services
  - Configuring PostgreSQL
  - Configuring PostgreSQL databases
Topics: ab, apachectl, curl, ftp, hwclock, mail, newaliases, nmblookup, ntpdate, ntpq, smbclient, smbpasswd, tzselect

## 14 Troubleshooting, performance, and security
Troubleshooting methodology
Resolving common system problems
  - Hardware-related problems
  - Software-related problems
  - User interface-related problems
Performance monitoring
  - Monitoring performance with `sysstat` utilities
  - Other performance monitoring utilities
Security
  - Securing the local computer
  - Protecting against network attacks
  - Using encryption to protect network data
  - Detecting intrusion
Topics: /etc/ld.so.cache, /etc/ld.so.conf, free, gpg, iostat, iptables, ldconfig, ldd, logger, lsof, lspci, lsusb, mpstat, nmap, nohup, sestatus, ssh-add, sar, su, sudo, sudo, ulimit, vmstat

##  A Certification
##  B GNU General Public License
##  C Finding Linux resources on the Internet
