# Day 12 - Virtualization Basics

## What I Studied

### Virtualization Basics
- Virtualization
- Hardware utilization
- Physical servers
- Resource sharing
- Scalability
- Isolation

### Hypervisors
- Hypervisor role
- Type 1 hypervisors
- Type 2 hypervisors
- VirtualBox
- VMware Workstation

### Virtual Machines (VMs)
- Virtual machines
- Guest operating systems
- Host operating systems
- Virtual CPU
- Virtual RAM
- Virtual storage
- Virtual networking
- Kali Linux VM

### Containers
- Containers
- Containerization
- Docker
- Container images
- Shared kernels
- Lightweight environments

### Operating System Concepts
- Kernel
- Resource management
- Isolation
- Host kernel
- Guest kernel

---

## What I Learned

Virtualization allows a single physical computer or server to run multiple isolated virtual systems called Virtual Machines (VMs).

Before virtualization, companies commonly used one physical server for one application, which caused poor hardware utilization and high infrastructure costs.

Hypervisors are responsible for creating and managing VMs while safely allocating hardware resources such as CPU, RAM, storage, and networking.

Type 1 hypervisors run directly on physical hardware and are commonly used in enterprise servers and cloud infrastructure.

Type 2 hypervisors run inside an existing operating system and are commonly used for learning, testing, and cybersecurity labs.

Virtual machines behave like real computers with their own operating systems, kernels, applications, storage, and networking.

Multiple VMs can share the same physical hardware while remaining isolated from each other.

Kali Linux can run safely inside a VM using software such as VirtualBox or VMware Workstation.

Containers are lightweight isolated application environments that share the host operating system kernel instead of running a full operating system.

Containers start faster and use fewer resources because they do not include separate kernels or full operating systems.

Docker is a popular platform used to deploy and manage containers.

Container images are prebuilt templates that contain applications, dependencies, libraries, and configurations used to create containers.

---

## Expanded Understanding

The hypervisor acts like a manager between the physical hardware and virtual machines.

Virtual machines are heavier than containers because each VM contains its own operating system and kernel.

Containers are not small virtual machines; they are isolated application environments sharing the host kernel.

The kernel is the core part of the operating system responsible for managing hardware resources, memory, processes, and communication with devices.

Containers must generally match the host operating system type because they share the host kernel.

Most cloud servers are actually virtual machines running on large physical servers inside data centers.

Virtualization is one of the foundational technologies behind modern cloud computing, cybersecurity labs, malware analysis, and scalable infrastructure.

Snapshots in VMs allow systems to be restored quickly after testing or experimentation.

Shared hosting differs from cloud servers because shared hosting places multiple websites inside the same environment, while cloud servers often provide isolated virtual machines.

---

## Key Terms

### Virtualization
Using one physical computer to create multiple virtual systems.

### Hypervisor
Software that creates and manages virtual machines.

### Type 1 Hypervisor
Hypervisor running directly on physical hardware.

### Type 2 Hypervisor
Hypervisor running inside an existing operating system.

### Virtual Machine (VM)
A full virtual computer with its own operating system and kernel.

### Host OS
The main operating system running on the physical machine.

### Guest OS
The operating system running inside a VM.

### Kernel
Core part of the operating system responsible for managing hardware and system resources.

### Container
A lightweight isolated application environment sharing the host kernel.

### Docker
Platform used to create and manage containers.

### Container Image
Prebuilt template used to create containers.

---

## Key Takeaway

Virtualization allows modern IT systems to maximize hardware efficiency while safely isolating environments. Hypervisors make it possible to run multiple virtual machines on the same physical hardware, while containers provide lightweight application isolation by sharing the host kernel. These technologies form the foundation of modern cloud computing, scalable infrastructure, and cybersecurity labs.
