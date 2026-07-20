# Linux File System

## Linux File System vs Windows File System

- Linux File System
  - hierarchical tree structure
  - 1 root folder and many sub folders
- Window
  - multiple root folders
    - disks and drives in the root
    - Removable Disks: A:, B:
    - Internal hard drive - Local Disk: C:
    - Data: D:

## Linux File System Overview

### home directory and root directory

- "/" is the root directory
  - Inside "/", there is a "/home" directory
  - "/home": contains home directories of all non-root users except root users
- "root"
  - Root users have isolated folder separated from other users
  - Root user's home directory is at "/root"
- Multiple users on computer
  - Each user has its own space (its own home directory)
  - Each user can have own configurations
- Programs installed system wide, are available for all users on that computer
  - outside the home directory

### /bin

- Definition:
  - system wide
  - stands for binaries
  - executables for most essential user commands
- contains the most basic commands available for the os
  - etc, cat, cp, echo
- what is binary?
  - computer-readable format, a format computers understand
    - 0,1
    - executed commands must be in binary formats and in binary files.

### /sbin - system binaries

- Definition:
  - essential system binaries programs that admin would use (need superuser previledge)
  - system itself also uses
- contains a bunch of commands but are system-relevant that these commands need super user permission to execute
- etc., adduser, chopasswd

### /Lib - Library

- Definition:
  - Essential shared libraries that executables from /bin or /sbin use

### /usr - user

- Definitions:
  - this was used for user home directories before "/home" is edited
- contains also /bin, /sbin and /lib, same structure and contents in the root folder
- Why?
  - historic reasons
  - because of storage Limitations it was split to root binary folders and user binary folders
  - now the storage is not limited, so there are duplicates in 2 places
- Whenever running the commands, the commands in the users' bin folder is normally executed
- In some os, there are fewer commands in bin and sin folders in the outer level.
- /usr/local
  - Inside the user folder, there is a "/local" folder containing /bin, /sbin, /lib
    - /usr/local is the place programs that YOU (linux user) install on the computer
    - third-party applications like docker, java
    - for example, when installing java, commands will go to /bin, library will go to /lib, documentation will go to somewhere else
  - programs installed here, will be available for all users on the computer
    - system wide applications and installations
    - If installing docker here, every users will be available to docker in their home space

### /opt - optional

- Definition:
  - another place third-party programs you install
  - system wide for all users
- Difference between /opt and /usr/local:
  - /usr/local: programs which split its components
  - opt: programs which not split its components into different directories
    - for example: most IDEs, web browsers

### /boot - booting

- Definitions:
  - contains files required for booting
- should never touch

### /etc - et cetera

- Definitions:
  - Place where configuration for system-wide applications are stored
  - originally for everything else
  - Later merged to main configuration location for different configuration, users, groups.
- before this directory, all folders are read-only, this is write-allowed

### /dev - devices

- Definition
  - location of device files - webcam, keyboard, hard drive etc.
  - Apps and Drivers will access this, NOT the user
  - files that the system needs to interact with the device

# /var - variable

- Definition
  - contains files to which the system writes data during the course of its operation
- /var/log: contains log files from different processes for running the computer
- /var/cache: contains cached data from application programs

### /tmp - temporary

- Definition:
  - temporary resources required for some process, kept here temporarily
  - At some point, the data will be deleted.

### /media and /mnt

- /media - removable media
  - Definition:
    - contains subdirectories, where removable external media devices inserted into the computer are mounted
  - for example, when you insert a CD. A directory will automatically be created and you can access the contents of the CD inside the directory. And they will also be referenced in the /dev folder
- /mnt - temporary mount points
  - Definition - historically, sys admins mounted temporary file systems there
    19941207
