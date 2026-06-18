# Day 31 – Windows Fundamentals 2

## TryHackMe Room

Windows Fundamentals 2

---

# Topics Covered

Today I started the Windows Fundamentals 2 room on TryHackMe.

This room focused on Windows system configuration tools, UAC settings, Computer Management, System Information, Resource Monitor, Command Prompt, and Registry Editor.

The main focus was learning what each built-in Windows tool is used for and which commands can be used to open them.

---

# Task 2 – System Configuration and Advanced System Settings

## System Configuration

System Configuration is mainly used for troubleshooting Windows startup and boot issues.

### Command

```cmd
msconfig
```

## Important Tabs

| Tab | Purpose |
|---|---|
| General | Controls startup mode |
| Boot | Controls boot options |
| Services | Shows configured services |
| Startup | Startup-related items; modern Windows often redirects to Task Manager |
| Tools | Lists useful Windows admin tools |

## Important Commands

| Command | Purpose |
|---|---|
| `control.exe` | Opens Control Panel |
| `msconfig` | Opens System Configuration |
| `taskmgr` | Opens Task Manager |
| `shell:startup` | Opens the current user Startup folder |

## Startup Folder

The Startup folder shows programs or shortcuts configured to run automatically when a user logs in.

```cmd
shell:startup
```

---

# Task 3 – Change UAC Settings

## User Account Control

User Account Control helps protect Windows by warning the user before apps or users make system-level changes.

## UAC Levels

| Level | Meaning |
|---|---|
| Always notify | Highest security; warns for apps and user changes |
| Notify me only when apps try to make changes | Default setting |
| Notify without dimming | Same as default, but the desktop does not dim |
| Never notify | Turns off warnings; not recommended |

## Key Takeaway

UAC is the Windows admin permission prompt.

Never notify is risky because Windows will not warn before system-level changes.

---

# Task 4 – Computer Management

## Computer Management

Computer Management is a Windows admin console that groups several management tools in one place.

### Command

```cmd
compmgmt.msc
```

## Main Sections

| Section | Contains |
|---|---|
| System Tools | Task Scheduler, Event Viewer, Shared Folders, Local Users and Groups, Performance, Device Manager |
| Storage | Disk Management |
| Services and Applications | Services and WMI Control |

---

## Task Scheduler

Task Scheduler is used to run programs, scripts, or tasks automatically.

### Command

```cmd
taskschd.msc
```

## Important Terms

| Term | Meaning |
|---|---|
| Task | The job Windows runs |
| Trigger | When the task runs |
| Action | What the task does |
| Task Scheduler Library | Where scheduled tasks are listed |

## Cybersecurity Note

Scheduled tasks can be used by administrators for automation and by attackers for persistence.

---

## Event Viewer

Event Viewer shows Windows logs and system events.

### Command

```cmd
eventvwr.msc
```

## Important Logs

| Log | Purpose |
|---|---|
| Application | App/program events |
| Security | Logons, authentication, audit events |
| Setup | Installation/setup events |
| System | System, services, and driver events |
| Forwarded Events | Events collected from other systems |

## Cybersecurity Note

Event Viewer is important because logs are evidence of activity on a Windows system.

---

## Shared Folders

Shared Folders shows folders shared over the network.

| Section | Meaning |
|---|---|
| Shares | Shared folders |
| Sessions | Users currently connected |
| Open Files | Files currently opened by connected users |

## Important Default Shares

| Share | Meaning |
|---|---|
| `C$` | Hidden admin share for the C drive |
| `ADMIN$` | Hidden admin share used for remote administration |

---

## Local Users and Groups

Local Users and Groups is used to manage local Windows accounts and groups.

### Command

```cmd
lusrmgr.msc
```

## Used For

- Viewing local users
- Managing local groups
- Checking group membership
- Reviewing permissions

---

## Performance Monitor

Performance Monitor is used for detailed performance monitoring.

### Command

```cmd
perfmon
```

## Used For

- CPU monitoring
- Memory monitoring
- Disk monitoring
- Network monitoring
- Performance logs

---

## Device Manager

Device Manager is used to view and manage hardware and drivers.

### Command

```cmd
devmgmt.msc
```

---

## Disk Management

Disk Management is used to manage disks, partitions, and drive letters.

### Command

```cmd
diskmgmt.msc
```

## Used For

- Set up new drives
- Extend partitions
- Shrink partitions
- Change drive letters
- View disk layout

---

## Services

Services are background programs that run without the user manually opening them.

### Command

```cmd
services.msc
```

## Startup Types

| Startup Type | Meaning |
|---|---|
| Automatic | Starts when Windows boots |
| Manual | Starts when triggered |
| Disabled | Prevented from starting |

## Cybersecurity Note

Attackers may abuse services for persistence, and administrators use services to manage background functions.

---

## WMI Control

WMI stands for Windows Management Instrumentation.

### Command

```cmd
wmimgmt.msc
```

## Important Note

WMIC is deprecated, but WMI itself still exists. PowerShell is the modern replacement for WMIC commands.

---

# Task 5 – System Information

## System Information

System Information shows detailed information about the computer, hardware, system components, and software environment.

### Command

```cmd
msinfo32
```

## Main Sections

| Section | Meaning |
|---|---|
| System Summary | Main computer specs |
| Hardware Resources | Low-level hardware details |
| Components | Hardware/device information |
| Software Environment | Windows/software details |

## System Summary

Shows general computer information such as:

- OS name
- OS version
- System manufacturer
- System model
- Processor
- BIOS version
- Installed RAM

## Components

Shows hardware device information such as:

- Display
- Input devices
- Network adapters
- Storage
- USB devices
- Sound devices

## Software Environment

Shows software and Windows-related information such as:

- Environment Variables
- Network Connections
- Running Tasks
- Services
- Startup Programs
- System Drivers

## Environment Variables

Environment variables store system values used by Windows and programs.

Example:

```text
WINDIR = location of the Windows installation folder
```

Usually:

```text
WINDIR = C:\Windows
```

---

# Task 6 – Resource Monitor

## Resource Monitor

Resource Monitor shows detailed live system resource usage.

### Command

```cmd
resmon
```

## Main Tabs

| Tab | Shows |
|---|---|
| Overview | Summary of CPU, Disk, Network, and Memory |
| CPU | Processor usage by processes |
| Memory | RAM usage by processes |
| Disk | Drive read/write activity |
| Network | Network activity by process |

## Key Takeaway

Task Manager gives a quick overview, while Resource Monitor gives deeper live details.

---

# Task 7 – Command Prompt

## Command Prompt

Command Prompt lets users interact with Windows by typing commands instead of using the GUI.

### Command

```cmd
cmd
```

## Commands Learned

| Command | Purpose |
|---|---|
| `hostname` | Shows the computer name |
| `whoami` | Shows the currently logged-in user |
| `ipconfig` | Shows network address settings |
| `ipconfig /?` | Shows the help manual for ipconfig |
| `cls` | Clears the Command Prompt screen |
| `netstat` | Shows TCP/IP connections and protocol statistics |
| `net` | Shows network-related subcommands |
| `net help` | Shows help for the net command |
| `net help user` | Shows help for net user |
| `net help localgroup` | Shows help for net localgroup |
| `net help use` | Shows help for net use |
| `net help share` | Shows help for net share |
| `net help session` | Shows help for net session |

## Important Syntax Note

The correct syntax is:

```cmd
net help user
```

Not:

```cmd
net user help
```

## Cybersecurity Importance

| Command | Why It Matters |
|---|---|
| `whoami` | Confirms which user account is active |
| `hostname` | Confirms which machine is being used |
| `ipconfig` | Shows network information |
| `netstat` | Shows network connections |
| `net help user` | Useful later for user/account enumeration |
| `net help localgroup` | Useful later for checking groups/admins |
| `net help share` | Useful later for shared folders/resources |
| `net help session` | Useful later for connected sessions |

---

# Task 8 – Registry Editor

## Windows Registry

The Windows Registry is a central database where Windows stores important configuration settings.

## Simple Meaning

The registry is the Windows configuration database.

## Registry Editor

### Command

```cmd
regedit
```

## Registry Stores Information About

- User profiles
- Installed applications
- File/document types
- Folder and icon settings
- Hardware on the system
- Ports and device information
- System and application settings

## Important Warning

The registry is for advanced users. Wrong changes can break Windows or applications.

## Cybersecurity Note

The registry matters in cybersecurity because it can contain startup and persistence settings, software traces, security settings, and system configuration changes.

---

# Commands Cheat Sheet

| Command | Opens / Does |
|---|---|
| `control.exe` | Opens Control Panel |
| `msconfig` | Opens System Configuration |
| `taskmgr` | Opens Task Manager |
| `shell:startup` | Opens the current user Startup folder |
| `compmgmt.msc` | Opens Computer Management |
| `taskschd.msc` | Opens Task Scheduler |
| `eventvwr.msc` | Opens Event Viewer |
| `lusrmgr.msc` | Opens Local Users and Groups |
| `perfmon` | Opens Performance Monitor |
| `devmgmt.msc` | Opens Device Manager |
| `diskmgmt.msc` | Opens Disk Management |
| `services.msc` | Opens Services |
| `wmimgmt.msc` | Opens WMI Control |
| `msinfo32` | Opens System Information |
| `resmon` | Opens Resource Monitor |
| `cmd` | Opens Command Prompt |
| `hostname` | Shows the computer name |
| `whoami` | Shows the current logged-in user |
| `ipconfig` | Shows network address settings |
| `ipconfig /?` | Shows help for ipconfig |
| `cls` | Clears the Command Prompt screen |
| `netstat` | Shows TCP/IP connections and protocol statistics |
| `net` | Shows net command subcommands |
| `net help` | Shows help for net |
| `net help user` | Shows help for net user |
| `net help localgroup` | Shows help for net localgroup |
| `net help use` | Shows help for net use |
| `net help share` | Shows help for net share |
| `net help session` | Shows help for net session |
| `regedit` | Opens Registry Editor |

---

# Key Takeaways

- `msconfig` is used for startup and boot troubleshooting.
- `taskmgr` is used to view processes, performance, and startup apps.
- `shell:startup` shows programs that run when a user logs in.
- `compmgmt.msc` opens a central admin console.
- `eventvwr.msc` is important for Windows logs.
- `services.msc` shows background services.
- `taskschd.msc` shows scheduled tasks.
- `lusrmgr.msc` shows local users and groups.
- `msinfo32` shows system information.
- `resmon` shows live resource usage.
- `cmd` is the Windows command-line tool.
- `regedit` opens the Windows Registry.
- The registry is powerful but risky to edit.

---

# Personal Notes

Today I learned how Windows provides many built-in tools for system configuration, troubleshooting, monitoring, and investigation.

The most important tools for cybersecurity at this stage are Event Viewer, Services, Task Scheduler, Local Users and Groups, Command Prompt, System Information, Resource Monitor, and Registry Editor.
