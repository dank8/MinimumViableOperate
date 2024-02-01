## NAME
 linux, a minimum viable operating instruction for generic linux

## SYNOPSIS

na

## DESCRIPTION
Random commandline reference for generic Linux. 

> NOTE: some commands are specific to the AlpineLinux flavour, but theres no time to go back and figure out which ones.

## INSTALLATION

1. choose your faviourte flavour

## INVOKE


### Standard commands

* [Linux commands](https://developers.redhat.com/cheat-sheets/advanced-linux-commands/?intcmp=701f20000012ngPAAQ)
* [Vim Find Next - VimTricks](https://vimtricks.com/p/vim-find-next/)
* [Linux man pages](https://linux.die.net/man/)
* [Software - GNU Project - Free Software Foundation](https://www.gnu.org/software/)

Source: [Lamisa Musharrat | Linux Simply](https://linuxsimply.com/lamisa-musharrat/)

#### Monitoring	

| command | description |
|:--:|:-- |
| top | Displays information about the active processes running on the system |
| htop | Shows a list of all the running processes throughout the system |
| vmstat | Shows detailed information about system performance, including memory usage, CPU utilization, and Input/Output (I/O) statistics |
| free | Displays the total amount of free and used memory in the system, as well as the buffers and cached memory used by the kernel |
| ps | Displays information about the active processes on the system, including their process ID (PID), CPU usage, memory usage, and other details |
| uptime | Displays how long the system has been running and the current system load averages |
| time | Measures the execution time of a command or script |
| dmesg | Displays the kernel ring buffer messages, which include system boot messages and other kernelrelated messages |
| finger  | Displays information about a user, including their login name, full name, home directory, login shell, and the time they last logged in |

#### System Information	

| command | description |
|:--:|:-- |
| free | Displays the amount of free and used memory in the system |
| ps | Displays a snapshot of the current processes |
| ps aux | Displays detailed information about all processes currently running |
| uptime | Displays the current uptime of the system |
| w | Displays the list of currently logged-in users |
| uname | Displays system information |
| uname -a | Displays detailed system information |
| hostname | Displays the name of the current host |
| info  | Provides access to the documentation of various installed software packages |
| lshw | Lists hardware configuration of the system |
| history  |  Displays a list of previously executed commands |
| help | Displays information about built-in shell commands\ |
| man | Displays the manual page for a specified command |
| tty  | Reports the file name of the terminal device that is currently used to interact with the shell |

#### Built-in	

| command | description |
|:--:|:-- |
| export | Sets environment variables that are used by processes started by the shell that exported the variable |
| echo | Displays text on the screen or redirects it to a file or variable |
| alias | Creates a shortcut or alternate name for a command |
| unalias | Removes an alias previously created with the 'alias' command. |
| exit | Closes the current shell or terminal session |
| clear | Clears the terminal screen |
| bash | Enables users to interact with Linux OS |
| declare | Declares variables and specifies their attributes, such as their data type or scope |
| source | Executes a script in the current shell environment rather than creating a new subshell to run the script |

#### Administration	

| command | description |
|:--:|:-- |
| sudo | Allows users to run programs with the security privileges of another user, typically the root user |
| sudo -s | Starts a shell with root privileges |
| sudo -s -u {user} | Starts a shell with the privileges of the specified user |
| sudo -k | Invalidates the user's cached credentials |
| sudo visudo | Opens the sudoers file for editing |
| sudo -H nautilus | Opens the file browser with root privileges |
| sudo /etc/init.d/k dm restart  | Restarts the GDM (GNOME Display Manager) service |
| sudo /etc/init.d/g dm restart  | Restarts the KDM (KDE Display Manager) service |
| passwd | Allows users to change their password |
| shutdown | Shuts down the system in a safe way |
| sync  | Forces all file system changes to be written to disk |
| reboot | Reboots the system |
| install  | Installs one or more packages on a Linux system using a package manager |
| setstatus  | Displays the status of the SELinux security system |
| service  | Controls system services, such as starting, stopping, and restarting them |
| getent | Retrieves entries from databases |
| env  | Displays the current environment variables or sets a new environment variable |
| jobs  | Displays a list of jobs running in the background of a shell |
| cron | Automates tasks to run at specified times or intervals |
| crontab | Schedules periodic commands or scripts to run at specified intervals |

#### Packages	

| command | description |
|:--:|:-- |
| apt-get update | Updates the list of available packages |
| apt-get upgrade | Upgrades all installed packages to their latest version |
| apt-get dist-upgrade | Upgrades all installed packages to their latest version |
| apt-get install pkg | Installs a package |
| apt-get purge pkg | Completely removes a package, including its configuration files |
| dpkg - configure -a | Configures all packages that have been unpacked but not yet configured |
| dpkg -i pkg.deb | Installs a package from a .deb file |
| snap  | Installs and manage applications on systems |
| apt-get  autoremove | Removes any packages that were installed as dependencies and are no longer needed |
| dpkg -l  | Applies a patch file to an original file, making the changes specified in the patch file Lists all installed packages |
| apt-get -f   | Attempts to fix any broken dependencies and install install missing packages |
| apt-get update | Updates the list of available packages |
| apt-get upgrade | Upgrades all installed packages to their latest version |
| apt-get dist- upgrade  | Upgrades all installed packages to their latest version |
| apt-get   | Completely removes a package, including its purge pkg configuration files |

#### Disk	

| command | description |
|:--:|:-- |
| lsblk | Lists information about all available or specified block devices and can also display the relationship between the different devices,such as partitions and logical volumes |
| enable | Enables or disables a service at startup or a specific hardware device or driver |
| df | Displays the disk usage statistics for the file system |
| df -h | Displays the disk usage statistics for the file system in human-readable format |
| du | Estimates the file space usage |
| fdisk | Allows users to create, delete, and modify partitions on hard drives, flash drives, and other storage devices |
| shred | Securely deletes files by overwriting them multiple times with random data |
| dd | Copies and converts data between files, partitions, and devices at the block level |
| mount | Mounts a file system, making it accessible at a specified mount point in the directory tree |
| mkfs | Creates a new file system on a specified device and supports various file system types such as ext2, ext3, ext4, NTFS, and FAT32 |
| mke2fs | Creates a new ext2/ext3/ext4 file system on a specified device |

#### Network	

| command | description |
|:--:|:-- |
| ip  | Displays and manipulates network interfaces and routing tables |
| ping  | Sends a packet to a host and measures the response time |
| ssh  | Remotely logs into a server or other device over a network |
| scp | Transfers files between hosts on a network |

#### Permissions	

| command | description |
|:--:|:-- |
| chmod | Changes the permissions of file and determines who can read, write, or execute a file |
| chown | Changes the owner and/or group of a file or directory |

#### User	

| command | description |
|:--:|:-- |
| useradd | Creates a new user account, including setting up a home directory and assigning a password |
| adduser | Creates a new user account interactively or using command-line options |
| who | Displays information about the users who are currently logged in |
| whoami | Displays the current username of the user who is logged in |
| id | Dissplays the user and group IDs of a specified user or the current user |
| usermod | Modifies a user account, such as changing the user's login name, password, home directory, or group membership |
| users | Displays a list of usernames of users who are currently logged in |
| su | Switches the current user to another user account, usually with elevated privileges, by prompting for the target user's password |
| chage | Modifies the password expiry information for a user |
| userdel | Deletes a user account and all associated files and directories |
| addgroup | Creates a new user group |
| groupadd | Creates a new user group |
| groupmod | Modifies the properties of an existing user group |

#### Firewall	

| command | description |
|:--:|:-- |
| wget | Downloads files from the internet |
| ifconfig | Shows network interface configuration |
| iwconfig | Shows wireless network interface configuration |
| sudo iwlist | Scans for available wireless networks |
| sudo systemctl restart  | Restarts the networking service networking.s ervice |
| ifup interface  | Brings up a network interface |
| ifdown interface | Brings down a network interface |
| firewall -cmd  | Allows users to configure and manage the firewall settings |
| ufw enable | Enables the firewall |
| ufw disable | Disables the firewall |
| ufw default allow | Sets the default policy to allow traffic |
| ufw default deny | Sets the default policy to deny traffic |
| ufw status | Shows the status of the firewall |
| ufw allow port | Opens a port |
| ufw deny port | Closes a port |
| ufw deny from ip | Blocks traffic from a specific IP address |

#### File System	

| command | description |
|:--:|:-- |
| ls | Lists files in a directory |
| ls -al | Lists all files in a directory, including hidden files, with detailed information |
| ls -R | Lists files in a directory and all of its subdirectories |
| ls -a | Lists all files in a directory, including hidden files |
| touch | Modifies timestamps of a file or creates an empty file if it doesn't exist |
| diff | Compares two files line by line and shows the differences between them |
| mkdir | Creates a new directory |
| pwd | Prints the current working directory |
| cd | Changes the current working directory to a specified directory |
| mkdir | Creates a new directorys |
| pwd | Prints the current working directory Installs a package |
| cd  | Changes the current working directory to a specified directory |
| cd ..     | Changes the current working directory to the parent directory of the current directory |
| patch   | Applies a patch file to an original file, making the changes specified in the patch file |
| rm [file]  | Removes a file |
| rm -r [dir]  | Removes a directory and its contents |
| rm -f [file]  | Forces the removal of a file |
| rm -rf [dir] | Forces the removal of a directory and its contents |
| cmp  | Compares two files byte-by-byte and reports the first byte and line that differs between them |
| comm   | Compares two sorted files line by line and displays the lines that are common or unique to each file |
| locate    | Searches for files in a database that contains a cached record of all files on the system |
| stat   | Displays detailed information about a file, including its size, permissions, owner, and modification time |
| cp | Copies files or directories |
| lsof  | Lists all open files and the processes that opened them |
| chgrp    | Changes the group ownership of files and directories |
| file    | Determines the type of a file by examining its contents |
| fsck | Checks and repairs a file system for errors |
| mv | Moves or renames files or directories |

#### Compression	

| command | description |
|:--:|:-- |
| zip | Archives files and directories into a compressed zip archive format |
| unzip | Extract the contents of a zip archive file |
| bzip2 | Compresses files using the Burrows-Wheeler block sorting text compression algorithm and Huffman coding |
| gzip | Compresses files using the Lempel-Ziv algorithm and Huffman coding |
| gunzip | Decompresses files that have been compressed using gzip |
| tar | Creates and manipulates archive files |

#### Text	

| command | description |
|:--:|:-- |
| wc | Counts the number of lines, words, and characters in a text file |
| sort | Sorts the lines of a text file in alphabetical or numerical order |
| nano | Allows users to create and edit text files |
| jed | Opens up a powerful text editor that supports multiple modes and macros |
| vi | Opens up a powerful text editor that uses modal editing to allow for quick and efficient editing |
| paste | Merges lines from multiple files and writes them to the standard output |
| egrep | Searches a text file for lines that match a specified pattern using extended regular expressions |
| cut | Extracts specific columns or fields from a text file |
| whereis | Locates the binary, source, and manual page files for a command |
| whatis | Displays a brief description of a command |
| which | Displays the location of a command or script in the system's PATH |
| at | Schedules a one-time command or script to run at a specified time |
| tee | Redirects the output of a command to a file and to the screen |
| date | Displays the current date and time |
| vim | Opens up a more advanced version of the vi editor with additional features such as syntax highlighting and plugins |
| split | Splits a text file into smaller files based on the number of lines or bytes |
| sed | A stream editor that performs editing operations on a text stream or file |
| tr | Translates or deletes characters in a text stream or file |
| uniq | Filters out duplicate lines from a sorted text file |
| cat | Displays the contents of a file on the terminal |
| head | Displays the first ten lines of a file on the terminal |
| tail | Displays the last ten lines of a file |
| grep | Searches for a specific pattern or text in a file or |
| less | Displays the contents of a file one page at a time, allowing scrolling back and forth |
| more | Display the contents of a text file one screen at a time allowing user to scroll up and down through the file, search for specific text, and navigate to specific lines |

#### Tools	

| command | description |
|:--:|:-- |
| bc | Command-line calculator that allows for floating-point arithmetic and advanced mathematical functions |
| ncal | Displays a calendar for a given month or year |
| neofetch | Displays system information and an ASCII art logo of the operating system |
| tree | Displays a directory tree structure in a hierarchical format |


### folder conventions:

| path           | purpose |
| ---            | --- |
| /              | the root, highest level directory of linix system |
| /home          | users personal data (sub-folder for each username) #user |
| /lib           | shared libraries #process |
| /opt           | manually installed third-party software (not installed by distribution and package manager) #process |
| /opt/bin       | links to the manually installed third-party binaries #process |
| /opt/doc       | documentation #process |
| /opt/lib       | third-party libraries #process |
| /opt/man       | third-party manpage #process |
| /run           | executable files #process |
| /srv           | data used by system services (https servers) #process |
| /tmp           | transient files are only avaliable until system is shutdown #process |
| /usr           | executable files, libraries, source of most of the system programs (normal users have readonly access) #process |
| /usr/bin       | binary files for basic user commands #process |
| /usr/sbin      | additional commands for the administrator #process |
| /usr/lib       | system libraries #process |
| /usr/share     | documentation or common to all libraries #process |
| /usr/share/man | text of the manpage #process |
| /var           | programs data that is persistant but temporary, logs & caches #process |
| /bin           | binary files for system shell commands. All Users #system |
| /boot          | kernal and boot image LILO and Grub #system |
| /etc           | system configuration files for the kernal and system administration #system; 
| /root          | system user data #system |
| /sbin          | system binaries. Only avaliable to the system administrators #system |
| /dev           | device data stream #device |
| /dev/null      | to send an object to 'nether' it gets destroyed #device |
| /dev/zero      | infinate string of zeros #device |
| /dev/random    | infinate sequence of random values #device |
| /media         | hot swapable and removable devices #device |
| /mnt           | connected device data and data-streams  #device |
| /proc          | currently running processes #device |



### cups

abstract: printer drivers
```lang-sh
apk add cups cups-libs cups-pdf cups-client cups-filters hplip

apk add cups hplip

bootup
rc-update add cupsd boot

open browser and add printer: http://localhost:631/
```

### alsa 

abstract: audio drivers

```lang-sh
apk add alsa-utils alsa-lib alsaconf alsa-ucm-conf
addgroup [root|users] audio

echo dependencies:
echo xfce component
apk add xfce-pulseaudio-plugin
```

### xfce 

abstract: GUI desktop manager ideas
- Text box to open any app
- simpler window switcher
- Edge fly out panels for apps and notes  (first alt-tab returns to current window)

### xfce plugin - clipman
 
abstract: clipboard tools for xfce destop mgr

```lang-sh
apk add xfce-clipman-plugin
```

### org.gentoo.openrc 

abstract: init packages

```lang-sh
openrc
rc-service #show services status
rc-sstat
rc-update
rc-status #all users
```

init:
* [server - How do I set an environment variable at boot time (via a script)? - Ask Ubuntu](https://askubuntu.com/questions/65563/how-do-i-set-an-environment-variable-at-boot-time-via-a-script)
* [How to Set Environment Variables in Linux {Step-by-Step Guide}](https://phoenixnap.com/kb/linux-set-environment-variable)
* [OpenRC - Gentoo Wiki](https://wiki.gentoo.org/wiki/OpenRC)
* [what does OpenRC do](https://www.phind.com/search?cache=f36008cb-0507-435b-9b0f-58395a4e709d)
* [OpenRC - ArchWiki](https://wiki.archlinux.org/title/OpenRC)
* [Create OpenRC Environment Variable](https://chat.openai.com/?model=text-davinci-002-render-sha)
* [OpenRC - Gentoo Wiki](https://wiki.gentoo.org/wiki/OpenRC)

### lang-c compiler
[Alpine Linux has switched to musl libc | Alpine Linux](https://www.alpinelinux.org/posts/Alpine-Linux-has-switched-to-musl-libc.html)

linux dynamic program loader
- [dynamic linking - How to change the path of shared libraries shown by ldd? - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/304140/how-to-change-the-path-of-shared-libraries-shown-by-ldd#304144)
- [Using newer libc on old Linux distributions](https://www.jertype.com/upgrading-glibc/)
- [Dynamic linker tricks: Using LD\_PRELOAD to cheat, inject features and investigate programs | Rafał Cieślak's blog](https://rafalcieslak.wordpress.com/2013/04/02/dynamic-linker-tricks-using-ld_preload-to-cheat-inject-features-and-investigate-programs/)
- [upgrade - How to update glibc to 2.14 in CentOS 6.5 - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/176489/how-to-update-glibc-to-2-14-in-centos-6-5)
- [Learning Linux Commands: export - Linux Tutorials - Learn Linux Configuration](https://linuxconfig.org/learning-linux-commands-export)


1. version and name of dynamic program loader
```lang-sh
 # ldd --version
 musl libc (x86_64)
 Version 1.2.3
 Dynamic Program Loader
 Usage: /lib/ld-musl-x86_64.so.1 [options] [--] pathname
```

1. find the libc file for each dynamic program loader
```lang-sh

 # apk musl --contents
/lib/libc.musl-x86_64.so.1

 # apk gcc -contents
/usr/lib/libcc1.so

 # gcc --print-file-name=libc.a
/usr/lib/gcc/x86_64-alpine-linux-musl/12.2.1/../../../../lib/libc.a
 # gcc --print-file-name=libc.so
/usr/lib/gcc/x86_64-alpine-linux-musl/12.2.1/../../../../lib/libc.so
```

1. set the current dynamic program loader
``lang-sh
export LD_LIBRARY_PATH=
export LD_PRELOAD=/usr/lib/libcc1.so ldd
sh /opt/calibre/linux-installer.sh
```
1. glibc packages [GCC - Alpine Linux](https://wiki.alpinelinux.org/wiki/GCC)

```lang-sh
apk add build-base
apk add gcc musl-dev libc-dev
```
1. musl-libc 

some possible files:
/usr/lib/libc.so
/usr/lib/libcc1.so

### apk 

abstract: package managers

Alternatives:
1. [Linux packages - org.pkgs](https://pkgs.org/api/)
  - abstract: collection of repositories and packages for Linux and Unix operating systems.
1. apk
  - update 
```lang-sh
apk add --upgrade apk-tools; echo "DONE> update package manager"
apk upgrade --update-cache --latest --available; echo "DONE> udpate packages"
cat /etc/alpine-release; echo "DONE> show alpine version"
cat cat /etc/apk/repositories; echo "DONE> show kernel version"

```
  upgrade all packages
    - `apk upgrade --update-cache --latest`
  - file owning package,  find out what package a file belongs to
    - `apk info --who-owns /sbin/lbu`
  - rollback packages
    - `lbu`


### lxc containerisation

abstract: native linux containers

running application in isolation
  - [chroot(2) - Linux manual page](https://man7.org/linux/man-pages/man2/chroot.2.html)

* [LXC Linuxcontainers.org](https://linuxcontainers.org/lxc/getting-started/)
* [LXC - Manpages](https://linuxcontainers.org/lxc/manpages/)
* [lxc](linuxcontainers.org/lxc)

```lang-sh
echo lxc depencency installation
apk add musl shadow shadow-subids libcap libapparmor libselinux libselinux gnutls lua python3-dev

echo unresolved
apk search libpam-cgfs
```

```lang-json
{ "faults": [ 
	{ "error": "lxc-checkconfig: unable to retrieve kernel configuration"
		"solution": "following logged message, Try modprobe configs module"
	},{ "error": "Cgroup v1 systemd controller: missing"
		"solution": "?"
	},{ "error": "Cgroup v1 freezer controller: missing"
		"solution": "
	}]
}
```

1. apk dependencies, Source: [LXC alpinelinux](https://wiki.alpinelinux.org/wiki/LXC)
  - `apk add lxc lxc-templates bridge lxcfs lxc-download xz`
1. installation
  - `apk add lxc`
1. create template
  - `lxc-create -n guest1 -f /etc/lxc/default.conf -t download`
    - --dist alpine --release 3.17 --arch amd64
1. start template
  - `lxc-start guest1`

```lang-yaml
faults: 
	- 
		error: lxc-start: guest1: ../src/lxc/network.c: netdev_configure_server_veth: 711 No such file or directory - Failed to attach "vethq2I3Tp" to bridge "lxcbr0", bridge 
```  

### cluster computing

abstract:  Beowulf cluster is a computer cluster of what are normally identical, commodity-grade computers networked into a small local area network with libraries and programs installed which allow processing to be shared among them. The result is a high-performance parallel computing cluster from inexpensive personal computer hardware. [Beowulf cluster (wikipedia), 2023](https://en.wikipedia.org/wiki/Beowulf_cluster)

As of 2014 a number of Linux distributions, and at least one BSD, are designed for building Beowulf clusters. These include:

- MOSIX, geared toward computationally intensive, IO-low applications
- ClusterKnoppix, based on Knoppix
- Kerrighed
- Rocks Cluster Distribution
- DragonFly BSD
- Quantian, a live DVD with scientific applications, based on Knoppix and ClusterKnoppix
- Kentucky Linux Athlon Testbed
- PelicanHPC, based on Debian Live

* [Setting up a home cluster | Blas M. Benito](https://www.blasbenito.com/post/01_home_cluster/)
* [what are the most recent linux cluster computing](https://www.phind.com/search?cache=deb528d3-94f3-46e1-8115-dde356d7a498)
* [know\_languages/README.md at main · dank8/know\_languages · GitHub](https://github.com/dank8/know_languages/blob/main/README.md)
* [Alpine Linux packages](https://pkgs.alpinelinux.org/packages)
* [ClusterLabs > Pacemaker Documentation](https://clusterlabs.org/pacemaker/doc/)
* [K8s - Alpine Linux](https://wiki.alpinelinux.org/wiki/K8s)
* [Beowulf cluster - Wikipedia](https://en.wikipedia.org/wiki/Beowulf_cluster)

As of 2014 a number of Linux distributions, and at least one BSD, are designed for building Beowulf clusters.

Stages of system deployment:

1. baremetal os deploy
  - [Tinkerbell](https://docs.tinkerbell.org)
1. Configure System, Provision packages, manage system
  - [Ansible - Alpine Linux](https://wiki.alpinelinux.org/wiki/Ansible)
  - [pyinfra](https://pyinfra.com/)
1. containerisation
  - [rocket](https://rocket.readthedocs.io/en/latest/README/)

* [IT Automation ebook](https://www.redhat.com/en/engage/system-administrator-guide-s-202107300146?intcmp=701f20000012ngPAAQ)

### tinkerbell

abstract: over the wire network distribute and install of linux OS using tinkerbell
- [Tink Server - Tinkerbell Docs](https://docs.tinkerbell.org/services/tink-server/)
- [architecture-diagram - tinkerbell.org](https://docs.tinkerbell.org/images/architecture-diagram.png)

1. Download OS image
  - [os image | Alpine Linux](https://alpinelinux.org/downloads/)
1. convert to raw
  - `apk add qemu-img`
  - `qemu-img convert [FilePath] -O raw [outputFilePath].raw`

### rocket rkt
* [rocket](https://rocket.readthedocs.io/en/latest/Documentation/trying-out-rkt/)

### sensors-detect

abstract: list of system sensors eg. cpu temperature
`apk add lm-sensors-detect`

### iwd (wifi drivers)

abstract: drivers for wifi hardware 

1. install
```lang-sh
apk add linux-firmware iwd
rc-service iwd start
```
2. usage:
```lang-sh
echo find stations
iwctl device list
iwctl station wlan0 scan && iwctl station wpl8x0 get-networks

echo connect
iwctl station wlan0 connect <SSID>
```

### acl 

abstract: access control
```
`ls -l` prints the following:
drwxr-sr-x    2 cain     cain          4096 May  4 10:40 2023-05-02
<Permit  > <ex> <User  > <Group > <...                            >
```
- Blue: directory
- Green: Executable
- Cyan: Symbolic link
- Yellow: Device
- Magenta: Image
- Red: archive
- Red/Black: broken link

  1. Permit {0,9}
    - File type: -
    - Permission settings: rw-r--r--
    - {1,3} Owner
    - {4,6} Group
    - {7,9} Users
  1. ext {11,11}
    - Extended attributes: dot (.)
  1. User {16,24}    
    - User name of owner
  1. Group {25,32}
    - Group name of owner

- `chmod`
  - abstract: Change file permissions
  
### df 

abstract: df, Print filesystem usage statistics

```lang-sh
df -a
```

### du

abstract: du, summarize disk space used for FILEs (or directories)

```lang-sh
du -bh -d 1
```

### find

abstract: find, search files and perform actions on them

```lang-sh
find . -name '*xfce*' -type d
```

### grep

abstract: grep, Search for PATTERN in FILEs (or stdin)

- Search file content
```lang-sh
grep -rnw '/path' -e 'text'
```

### top 

abstract: prints the part of a file (from top or end) 
```
top -d=3 -w=6
~ $ top -d 3 -w 6 -o PID -o USER,PR,NI,%CPU,%MEM,TIME,COMMAND
```

### shift

abstract: moves all arguments the the left, by the number provided, useful inside of bash scripts

```lang-sh
shift 2;
```

### xdg-mime

abstract: xdg-mime, command line tool for querying information about file type handling and adding descriptions for new file types
```lang-sh
echo ?? unsure
xdg-mime query filetype ./Linux Journal 2023-04.md 
echo query the applications for a MimeType
xdg-mime query default text/markdown
echo uninstall a MimeType
xdg-mime uninstall text/markdown
echo uninstall all MimeType for application 
xdg-mime uninstall --mode user firefox.desktop
```

### bash 

#### alternatives:

- bash (gnu.org)
  - [gnu - Bash - GNU Project - Free Software Foundation](https://www.gnu.org/software/bash/)
  - [stackE - bash - How to correctly add a path to PATH? - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/26047/how-to-correctly-add-a-path-to-path)
  - [stackE - bash - Difference between .bashrc and .bash\_profile - Super User](https://superuser.com/questions/183870/difference-between-bashrc-and-bash-profile/183980#183980)
  - [gnu - Bash Manual](https://www.gnu.org/software/bash/manual/bash.html)
  - [wooledge - WordSplitting - Greg's Wiki](http://mywiki.wooledge.org/WordSplitting)
- ash (BusyBox) 

#### links worth keeping:

* [stackE - Posts containing 'command output' - Stack Overflow](https://stackoverflow.com/search?q=%5Bbash%5D+command+output+)
* [stackE - shell - How do I set a variable to the output of a command in Bash? - Stack Overflow](https://stackoverflow.com/questions/4651437/how-do-i-set-a-variable-to-the-output-of-a-command-in-bash)
* [stackE - shell script - bash loop through list of strings - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/450944/bash-loop-through-list-of-strings)
* [stackE - Accessing bash command line args $@ vs $\* - Stack Overflow](https://stackoverflow.com/questions/12314451/accessing-bash-command-line-args-vs)
* [stackE - Ash profile/configuration file - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/176027/ash-profile-configuration-file)
* [stackE - bash - How to correctly add a path to PATH? - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/26047/how-to-correctly-add-a-path-to-path)
* [wiki - Booting process of Linux - Wikipedia](https://en.wikipedia.org/wiki/Booting_process_of_Linux)
* [stackE - bash - Difference between .bashrc and .bash\_profile - Super User](https://superuser.com/questions/183870/difference-between-bashrc-and-bash-profile/183980#183980)
* [gnu - Bash Reference Manual](https://www.gnu.org/software/bash/manual/bash.html#Pipelines)
* [stackE - shell script - bash loop through list of strings - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/450944/bash-loop-through-list-of-strings)
* [stackE - Accessing bash command line args $@ vs $\* - Stack Overflow](https://stackoverflow.com/questions/12314451/accessing-bash-command-line-args-vs)
* [stackE - scripting - Does the shebang determine the shell which runs the script? - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/87560/does-the-shebang-determine-the-shell-which-runs-the-script)


glob pattern matching:
* [stackE - regex - Pattern matching in if statement in bash - Stack Overflow](https://stackoverflow.com/questions/45807613/pattern-matching-in-if-statement-in-bash)
* [stackE - bash - String pattern-matching with =\~ - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/415839/string-pattern-matching-with)
* [stackE - linux - Bash script pattern matching - Stack Overflow](https://stackoverflow.com/questions/44688460/bash-script-pattern-matching)


## EXPLANATORY NOTES

1. NONE

## DEPENDENCIES

NONE