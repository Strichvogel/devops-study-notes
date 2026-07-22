# Command Line Basics - Basic Linux Commands

## Overview

1. Basic linux commands can be executed in the command line interface (cli) to:

- work with the file system to:
  - create folders
  - list files in directory
  - rename and remove files
- Display operating system infos

2. GUI vs. CLI

1) Concepts

- GUI = A graphical user interface, where we have graphical elements that you can interact with, like buttons
- CLI vs. Terminal:
  - CLI = Command Line Interface, where users type in commands and see the results printed on the screen
  - Terminal = the GUI window that you see on the screen. It takes commands and shows output
- On servers you only have the CLI

2. When to use CLI or GUI?

- Why use CLI over GUI?
  - Work more efficient
  - Instead of clicking through file system, work in 1 terminal
  - Easier for bulk operations
  - CLI is more powerful

- Why use GUI?
  - Visual tasks, like video editing

3. Basics of terminal:

- format: username@computer_name: ~$
  - if on a server, the computer name will be the host name of the computer
    - when doing a stuff on multiple computers, it is important to know which computer
  - : is separator
  - ~ = home directory of the user
  - $ = represents regular user on a os, not a super user
    - if it is a root user, it will be "#". For example: root@VirtualBox:~#

## Operations

### Directory Operations

- pwd = print working directory
  - show current directory
- ls = List folders and files
- cd [dirname] = Change directory to [dir]
  - how to go to root folder: cd /
- mkdir [dirname] = make directory [dirname]
- rm -r [dirname] = delete a non-empty directory and all the files within it
- rm -d [dirname] or rmdir [dirname] = delete an empty directory

### File Operations

- touch [filename] = create [filename]
- rm [filename] = delete [filename]

#### tips:

- clear = clears the terminal
- everything in linux is a FILE including:
  - Text documents, Pictures etc.
  - Directories
  - Commands, like pwd, ls etc.
  - Devices, like Printer, Keyboard, USB, CD
  - so you can treat them as files using cli

### Navigating in the file system

- cd [absolute path] = move to any location by providing the full path
- ls [absolute path] = list the files and folders without going to the directory

### More File and Directory Operations

- mv [original filename] [new filename] = rename the file to a new filename
- cp -r [original dirname] [new dirname] = copy dirname to new_dirname
- cp [original filename] [new filename] = copy filename to new_filename
- ls -R [dirname]: list all directories and the files inside all the directories
- history = Gives a list of all past commands typed in the current terminal session
- ctrl + r: search history
- ctrl + c = stop current command
- ctrl + shift + v = Paste copied text into terminal
- ls -a = display all files and folders including hidden files and folders
- cat [filename] = Display the file content

## Display OS information

- uname -a = show system and kernel
- cat /etc/os-release
  - MacOS则是/usr/bin/sw_vers
- lscpu = show cpu info
- lsmem = show memory info

## Execute commands as superuser

- sudo = Allows regular users to run programs with the security privileges of the superuser or root
  - when using it, it will ask passwords
  - once authenticated, the passwords will be saved so you don't have to retype the passwords
  - example: sudo adduser [username]
- su - [username]: switch between users on one computer
- .bash_history: saves the history of the commands
  - On MacOS, it is .zsh_history
