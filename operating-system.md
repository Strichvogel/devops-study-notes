# Operating System Basic Concepts

## What is an operating system?

- Computers have hardware such as CPU, memory, storage and I/O devices
- Applications don't know how to talk to the hardware. Applications like browser can't be installed directly on the hardware.
- Operating system serves as a intermediatory layer to communicate with hardware and applications.

## What is operating system tasks? - Hardware resource allocation and management

1. Process Management - Managing CPU Resources

- What is a process?
  - small unit that executes on the computer
  - each process has own isolated space (so that they won't interfere with each other)
- 1 CPU
  - can only process 1 process at a time
  - 1 CPU can only process 1 task at a time at the background
  - CPU is switching so fast that you don't notice it
- Multiple CPU
  - Dual-Core = 2 CPU's (or 2 processes)
  - Quad-Core = 4 CPU's (or 4 processes)
- The more CPU's, the faster the applications work

2. Memory Management

- Memory management means allocating working memory to different processes
  - working memory is RAM (Random Access Memory): actively processing data
- every application needs some data to work (so need memory)
- RAM is limited on the computer
  - Memory Swapping
    - Definition: os unloads or clears the memory for application 1 and saves it in the secondary memory (storage), and then load the new process's data in the cleared memory. So how memory is allocated to different processes is memory management.
    - OS swaps memory between applications
    - one app becomes inactive, new one gets memory resources
    - slows down the computer because swapping takes time

3. Storage Management

- also called secondary memory
- persisting data long-term
- hard drive
- storage saves:
  - files
  - browser configurations
  - games
  - pictures
  - videos
- Storing these data and allocating some space for them also is managed by os
- Manage File System
  - os stored in a structured way
  - in Unix systems: tree file system - one root directory and sub-folders
  - in Windows OS: multiple root folders

4. Management of I/O Devices

- Devices include screen, keyword, mouse, printer, external storage
- When these connecting to computer, OS knows how to handle and translate interactions between apps and devices

5. Security & Networking

1) Security

- Managing users and permissions
- can have multiple users, each user has its own space
- each user has permissions: admin or non-admin

2. Networking

- assigning ports and IP addresses

## How an OS is constructed or made up?

### Operating System Components

1. Core part: Kernel - This is the part of the os that loads first

- Definition:
  - Kernel is a program that consists of device drivers, dispatcher, scheduler, File System etc.
  - Heart of every Operating System responsible for managing the hardware components (CPU, Memory, RAM).
- Different OS has different kernels
- Kernel handles I/O devices using various Device Drivers, which are code or programs that will allow external devices to interact with your computers
- Kernel is the layer between applications and hardware. When starting an application, it's the kernel that starts the process for the app, loads it into memory and allocate resources (etc,. CPU) to app. When closing the app, all resources will be cleaned up by the kernel.

2. Application layer (on top of kernel)

1) Operating systems types

- 3 Main Operating Systems: Linux, Windows, MacOS
  - Linux kernel
    - Linux kernel is most widely used
    - There are different Linux distributions, which have different application layers, but based on same Linux kernel.
      - such as Ubuntu, Mint, CentOS, Debian
      - Android is also based on Linux kernel.
  - Darwin kernel
    - macOS: originally called OS X
    - iOS
  - Windows
  - Tips:
    - each OS has many versions
    - MacOS vs Linux
      - Command line, file structure etc. similar
      - Where Windows is completely different
      - UNIX:
        - codebase for many different OS
        - Developed independent of Linux
        - Many OS built on top of Unix
        - MAcOS kernel Darwin is based on Unix
        - To keep them compatible, standards were introduced
        - POSIX is the most popular standard (Portable Operating System Interface)
      - Linux:
        - Linux was developed in parallel to UNIX based OS
        - Created by Linux Trovalds
        - No source code of UNIX
        - Clone of UNIX or also called "unix like"
        - Linux and MacOS both POSIX compliant
- Client OS vs Server OS
  - Operating systems for servers:
    - Linux and Windows have server distributions. Mostly based on Linux.
    - More light-weight and performant (running the hardware more efficiently)
    - No GUI or other user applications or I/O devices, just a command line interface to interact with the machine
  - Client OS
    - have GUI and I/O Devices

2. How to interact with Kernel: kernel cannot be accessible without the os user layer

- Graphical user interface
- Command line interface

3. User Apps (on top of application layer)

# Virtualization & Virtual Machines

1. What is a virtual machine?

- With virtualization, there is no need for separate hardware
- Can build a new OS based on a current OS using hypervisor. which allows posting multiple virtual computer on a physical computer.
- VirtualBox - one of the most popular hypervisor
  - from Oracle
  - Open-source
  - Works on all OS
  - VirtualBox takes hardware resources from Host OS
  - Creates virtual CPU, virtual RAM, virtual storage for each virtual machine
  - You can only give resources you actually have
  - Hardware resources are shared
- Virtual machines are completely isolated.
  - They don't know each other and they don't know them are virtual machine hosted on top of another system.
  - If something breaks inside VM, it doesn't affect the host machine. when this happened, can directly delete the VM and create a new one.

2. Benefits of a virtual machine

- learn and experiment
  - You don't need to buy a new computer for that
  - You don't endanger your main OS
- Test your app on different OS

3. 2 types of hypervisors

1) Type 1

- Structure
  - Guest OS
  - Hypervisor:
    - install directly on hardware and control the hardware resources
    - also called Bare Metal hypervisor
    - example: vmware ESXi, Microsoft Hyper-v
  - Hardware
- How work: For a big server, have 1 physical server and a bare metal hypervisor installed on it, and multiple vm running on the hypervisor, all sharing the same hardware resources
- Use Cases:
  - big cloud platform to create whole infrastructure
  - what are the benefits for companies using virtualization?
    - Efficient usage of hardware resources
      - Use all the resources of a performant big server
      - Users can choose any resource combinations
    - Abstraction of the OS from the hardware
      - with virtualization, the OS is a portable file that can be moved around.
      - The file is Virtual Machine Image, which includes:
        - Operating System
        - And all applications on it
      - Can have backups of your entire OS, namely the image
        - The backup is called snapshot
        - If the VMI is damaged or hacked, can use the snapshot and run it on the different computer with the hypervisor on it.
      - Benefits:
        - Secure very easily
        - Portable
        - Not dependent on physical server

2. Type 2: typically used for personal computers

- Guest OS: borrows hardware from the Host OS
- Hypervisor
- Host OS
- Hardware
