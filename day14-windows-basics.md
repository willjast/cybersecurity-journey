# Day 14 - Windows Basics

## Overview
Today I completed the Windows Basics room in TryHackMe using a Windows Server 2019 virtual workstation environment. This room focused on understanding the Windows graphical interface, user authentication, file management, system settings, application management, process monitoring, and built-in Windows security tools.

---

# Topics Covered

## Introduction to Windows
- Learned the evolution of Microsoft Windows from MS-DOS to modern Windows systems
- Understood how graphical user interfaces (GUI) replaced command-line interaction
- Learned how modern Windows combines usability, file management, security, and system administration tools

---

# Authentication and User Accounts

## Authentication
Authentication is the process of verifying identity before accessing the system.

Examples:
- Passwords
- PINs
- Biometrics

## Authorization
Authorization determines what actions a user is allowed to perform after logging in.

## Windows Account Types
### Guest Account
- Limited temporary access
- Cannot make system changes

### Standard User
- Used for normal daily tasks
- Limited system permissions

### Administrator
- Full control over the operating system
- Can install software and manage users

## Extended Learning
- Learned about the Principle of Least Privilege
- Understood why running daily activities as Administrator increases security risks
- Learned that malware running under Administrator privileges can cause severe system compromise

---

# Windows Desktop Environment

## Desktop
- Main workspace containing files, folders, and shortcuts

## Taskbar
- Used for navigation and accessing running applications
- Contains Start Menu, pinned applications, notifications, network, and audio settings

## Start Menu
- Central location for applications, settings, and power options

## Search Function
- Quickly locate applications, settings, and files

## Task View
- Displays open windows and virtual desktops

## Notifications Area
- Displays alerts and system status information

## Extended Learning
- Learned that modern Windows power users rely heavily on keyboard shortcuts and search functionality instead of manually browsing menus

---

# File Explorer and File Management

## File Explorer
- Built-in Windows tool for managing files and folders

## Hierarchical File Structure
Windows organizes data using folders and subfolders.

Example:
C:\Users\Administrator\Desktop\TryHatMe Onboarding

## File Paths
Learned how Windows paths identify exact file locations.

## File Searching
Used File Explorer search functionality to locate files and folders.

## Extended Learning
- Learned the importance of file paths in cybersecurity investigations
- Learned how analysts navigate systems using directories and paths
- Learned differences between Windows path separators "\" and Linux "/"

---

# Applications and Software Management

## Updating Applications
Learned that updates provide:
- Security patches
- Bug fixes
- Performance improvements

## Windows Update
- Built-in Windows updating system

## Installing Applications
Methods:
- Microsoft Store
- Downloading installers from trusted vendors

## Installer File Types
- .exe
- .msi

## Uninstalling Applications
Methods:
- Settings
- Control Panel
- Built-in uninstallers

## Extended Learning
- Learned that outdated software is a major cybersecurity risk
- Learned that fake installers are commonly used to distribute malware
- Learned importance of downloading software only from trusted vendors

---

# Windows Settings and Control Panel

## Windows Settings
Modern interface for:
- Personalization
- Updates
- Accounts
- Security
- Devices

## Control Panel
Legacy administrative interface still used for advanced system configuration.

## Extended Learning
- Learned that many IT professionals still rely on Control Panel for advanced administrative tasks

---

# Task Manager

## Purpose
Used to monitor system activity in real time.

## Task Manager Tabs

### Processes
- Running applications and background processes

### Performance
- CPU, memory, disk, and network usage

### Users
- Logged-in users and resource usage

### Details
- Advanced process information including Process IDs (PIDs)

### Services
- Background Windows services

## Extended Learning
- Learned that every running application is a process
- Learned that cybersecurity analysts often investigate suspicious processes and PIDs
- Learned how Task Manager assists in troubleshooting performance issues

---

# Windows Security

## Windows Security Sections

### Virus & Threat Protection
- Malware scanning and real-time protection

### Firewall & Network Protection
- Controls incoming and outgoing traffic

### App & Browser Control
- Helps block unsafe files and websites

### Device Security
- Hardware-based security protections

## Extended Learning
- Learned that security is layered and not dependent on a single antivirus solution
- Learned importance of real-time protection and threat scanning

---

# Windows Defender Firewall

## Purpose
Filters network traffic entering and leaving the system.

## Network Profiles

### Domain
- Corporate or organizational networks

### Private
- Trusted home or lab networks

### Public
- Untrusted public networks

## Firewall Rules
Rules determine whether traffic is allowed or blocked.

## Extended Learning
- Learned the difference between inbound and outbound traffic
- Learned that firewalls are a core part of network security defense

---

# Virtual Workstation Activities Performed

During the TryHackMe virtual lab, I:

- Logged into a Windows Server 2019 Administrator account
- Explored the Windows Desktop and Taskbar
- Used the Start Menu and Search functionality
- Opened and navigated File Explorer
- Viewed system information using About Your PC
- Explored the TryHatMe Onboarding folder
- Viewed full file paths
- Installed the TryHatMeWelcome application installer
- Explored Windows Settings and Control Panel
- Opened and analyzed Task Manager tabs
- Opened Windows Security
- Performed a custom antivirus scan on the onboarding folder
- Investigated scan results and viewed detected test files
- Explored Windows Defender Firewall settings and rule management

---

# Key Cybersecurity Concepts Learned

- Authentication vs Authorization
- Principle of Least Privilege
- Administrative privilege risks
- Process monitoring
- File system navigation
- Security patching and updates
- Malware detection basics
- Firewall traffic filtering
- Network security profiles
- Layered security approach

---

# Important Shortcuts Learned

| Shortcut | Function |
|---|---|
| Windows Key | Open Start Menu |
| Windows + E | Open File Explorer |
| Windows + I | Open Settings |
| Ctrl + Shift + Esc | Open Task Manager |
| Windows + Tab | Open Task View |
| Alt + Tab | Switch applications |

---

# Key Takeaway

Windows is much more than a graphical interface. It is a complete operating system that manages files, processes, users, permissions, applications, memory, networking, and security. Understanding how Windows works internally is an important foundation for future cybersecurity, system administration, and troubleshooting skills.
