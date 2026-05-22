# Day 13 - Cloud Computing Fundamentals and Operating Systems Introduction

## What I Studied

### Cloud Computing Fundamentals
- Cloud computing
- Virtualization in cloud computing
- Containers and cloud infrastructure
- Cloud scalability
- Elasticity
- Redundancy
- Cloud regions
- EC2 instances
- Instance types
- Public cloud
- Private cloud
- Hybrid cloud
- IaaS
- PaaS
- SaaS
- Cloud billing and cost optimization
- Cloud providers
- Data centers

### Operating Systems Introduction
- Operating systems
- Kernel
- Kernel space
- User space
- System calls
- Process management
- Memory management
- Virtual memory
- File system management
- Authentication
- Permissions
- Isolation
- GUI
- CLI
- Linux distributions
- Desktop operating systems
- Server operating systems
- Mobile operating systems
- Embedded operating systems
- Virtual/cloud operating systems
- Linux file systems
- ext4 file system

---

## What I Learned

Cloud computing provides scalable internet-based infrastructure and services instead of relying on local physical hardware.

Modern cloud computing is built on top of:
- virtualization
- containers
- networking
- automation

Virtualization allows physical servers to run multiple virtual machines efficiently, while containers provide lightweight isolated application environments.

Cloud providers use massive global data centers combined with virtualization, automation, and orchestration to dynamically provide computing resources.

Scalability refers to a system’s ability to grow and handle increased demand.

Elasticity refers to the cloud’s ability to automatically increase or decrease resources depending on workload and traffic demand.

Redundancy means having backup systems or resources available so services continue functioning if failures occur.

Cloud regions are geographic locations where cloud infrastructure is hosted. Regions improve:
- latency
- redundancy
- legal compliance

EC2 instances are cloud-based virtual machines that can be created, resized, stopped, or deleted dynamically.

Different instance types provide different levels of CPU and RAM resources depending on workload requirements.

Cloud computing allows organizations to pay only for the infrastructure they use instead of purchasing expensive physical hardware.

IaaS provides virtual infrastructure such as servers and storage.

PaaS provides a managed environment for developing and running applications.

SaaS provides fully managed software accessed through the internet.

Operating systems act as the central manager between applications, users, and physical hardware.

The kernel is the core component of the operating system responsible for managing hardware and system resources.

Kernel space is the highly privileged protected area where the kernel operates with direct hardware access.

User space is the restricted area where normal applications run safely with limited permissions.

Applications communicate with the kernel using system calls when requesting services such as file access, networking, or memory allocation.

The operating system manages:
- processes
- memory
- files
- devices
- users
- permissions
- security

Memory management allows the OS to allocate RAM safely between running applications.

Virtual memory allows the operating system to temporarily use disk storage when RAM becomes limited.

File systems organize and manage how files are stored on disks.

The ext4 file system is one of the most common Linux file systems.

GUI provides visual interaction through windows, icons, and menus.

CLI allows direct text-based interaction with the operating system using commands.

Linux is not one single operating system but a family of distributions such as:
- Ubuntu
- Debian
- Fedora
- Kali Linux

Different operating systems are optimized for different environments such as:
- desktop
- server
- mobile
- embedded
- cloud infrastructure

---

## Expanded Understanding

A massive data center alone does not automatically mean cloud computing. True cloud infrastructure requires virtualization, automation, scalability, and dynamic resource management.

Containers are not small virtual machines. Containers share the host operating system kernel instead of including their own operating systems and kernels.

Cloud infrastructure evolved from:
- physical servers
- virtualization
- containers
- automated scalable infrastructure

Cloud systems are designed to avoid single points of failure through redundancy and distributed infrastructure.

Dedicated servers, VPS hosting, shared hosting, and cloud computing are different infrastructure models with different levels of scalability, isolation, and flexibility.

Cloud providers dynamically create and destroy virtual infrastructure instead of relying on fixed hardware allocations.

The kernel is not a physical CPU core. The term "core" refers to the central controlling component of the operating system.

Kernel space and user space are real privilege separation layers designed for security and system stability.

Most modern cybersecurity infrastructure heavily relies on:
- Linux servers
- virtualization
- cloud computing
- containers
- CLI-based administration

Many cloud and server environments operate headlessly without graphical interfaces and are managed remotely through CLI access.

Operating systems themselves provide foundational security before antivirus or security tools are added.

Privilege separation and process isolation are critical security concepts that prevent applications from directly controlling hardware or interfering with other processes.

---

## Hands-On Practice

### Cloud Computing Practice
- Deployed EC2-style cloud virtual machines
- Selected cloud regions
- Configured instance types
- Managed virtual machine states
- Stopped cloud instances to reduce infrastructure cost
- Observed billing and cost optimization changes
- Practiced basic IaaS cloud management concepts

### Operating System Practice
- Explored Ubuntu Linux desktop environment
- Used System Monitor to inspect system information
- Viewed file system information
- Identified the ext4 Linux file system
- Navigated Linux home directories
- Investigated user directories and files
- Explored the Documents directory
- Retrieved information from files during investigation tasks

---

## Key Terms

### Cloud Computing
Scalable internet-based infrastructure and services.

### Scalability
Ability of a system to handle increasing demand.

### Elasticity
Automatic scaling of resources up or down depending on demand.

### Redundancy
Backup systems/resources that maintain availability during failures.

### Region
Geographic location of cloud infrastructure.

### EC2 Instance
Cloud virtual machine/server.

### IaaS
Infrastructure as a Service.

### PaaS
Platform as a Service.

### SaaS
Software as a Service.

### Operating System (OS)
Software that manages hardware, applications, and system resources.

### Kernel
Core component of the operating system managing hardware and resources.

### Kernel Space
Highly privileged protected operating system area.

### User Space
Restricted environment where regular applications run.

### System Call
Request from applications to the kernel for services.

### GUI
Graphical User Interface.

### CLI
Command-Line Interface.

### ext4
Common Linux file system.

### File System
Structure used by the OS to organize and store files.

---

## Key Takeaway

Modern computing infrastructure heavily depends on operating systems, virtualization, cloud computing, and containers working together. Cloud computing builds on virtualization, networking, and automation to provide scalable and flexible infrastructure, while operating systems enforce resource management, privilege separation, process isolation, and system security. Understanding these concepts forms a critical foundation for cybersecurity, Linux administration, cloud security, and modern IT infrastructure.
