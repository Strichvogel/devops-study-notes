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
