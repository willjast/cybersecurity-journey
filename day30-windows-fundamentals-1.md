# Day 30 – Windows Fundamentals 1

## TryHackMe Room

Windows Fundamentals 1

---

## Topics Covered

* Connecting to a Windows machine with Remote Desktop Protocol
* Understanding the NTFS file system
* NTFS permissions
* Alternate Data Streams
* Windows system folders
* Environment variables
* Windows user accounts and profiles
* User Account Control
* Windows Settings and Control Panel
* Task Manager

---

## Remote Desktop Protocol

Remote Desktop Protocol, or RDP, allows a user to connect to and interact with another Windows computer through a graphical desktop session.

The remote connection requires:

* The target computer’s IP address or hostname
* An authorized username
* The account password
* RDP access to be enabled and reachable

For the TryHackMe lab, I used an RDP client rather than SSH.

### RDP vs SSH

| Protocol | Typical purpose                                              |
| -------- | ------------------------------------------------------------ |
| RDP      | Graphical remote access to a Windows desktop                 |
| SSH      | Command-line remote access, commonly used with Linux systems |

Remote support tools that request permission before allowing control are different from a normal RDP login. RDP normally authenticates using an authorized Windows account.

---

## The Windows File System

Modern Windows installations commonly use the New Technology File System.

```text
NTFS = New Technology File System
```

Older Windows file systems include:

* FAT16
* FAT32
* HPFS

FAT file systems are still commonly used with removable storage such as USB drives and memory cards.

---

## NTFS Features

NTFS provides several features that were limited or unavailable in older file systems:

* Support for files larger than 4 GB
* File and folder permissions
* File and folder compression
* Encryption through EFS
* Journaling and recovery support

---

## NTFS Journaling

NTFS is a journaling file system.

It keeps records of file-system changes so Windows can use the recorded information to help recover from crashes, power failures, or incomplete operations.

```text
Journaling = recording file-system changes to support recovery
```

---

## NTFS Permissions

NTFS permissions control what users and groups may do with files and folders.

| Permission           | General meaning                                     |
| -------------------- | --------------------------------------------------- |
| Read                 | View a file or folder and access its contents       |
| Write                | Add or change data                                  |
| Read & Execute       | View contents and run executable files              |
| List Folder Contents | View the files and subfolders inside a folder       |
| Modify               | Read, write, and delete                             |
| Full Control         | Perform all actions, including changing permissions |

### Simple comparison

```text
Read = view

Write = add or change data

Read & Execute = view and run

Modify = read, write, and delete

Full Control = complete control, including permissions
```

Permissions can be assigned directly to users or inherited through group membership.

---

## Alternate Data Streams

Alternate Data Streams, or ADS, is an NTFS feature that allows a file to contain more than one stream of data.

Every file has a normal data stream, commonly identified as:

```text
$DATA
```

ADS allows additional information to be attached to a file without appearing as a separate file in File Explorer.

### Security relevance

ADS can have legitimate and malicious uses.

Legitimate example:

* Windows can mark a file as having been downloaded from the Internet.

Malicious example:

* Malware may use ADS to hide information from normal file-system views.

```text
ADS = additional data attached to an NTFS file
```

---

## The Windows Folder

Windows operating-system files are commonly stored in:

```text
C:\Windows
```

Although this is the normal location, Windows can technically be installed on another drive or in another folder.

---

## The `%windir%` Environment Variable

Windows uses the following environment variable to represent the Windows installation directory:

```text
%windir%
```

On a typical system:

```text
%windir% = C:\Windows
```

Using an environment variable is more reliable than assuming Windows is always installed in the same location.

---

## Environment Variables

Environment variables store information about the operating-system environment.

They may represent:

* System paths
* The Windows installation directory
* Temporary file locations
* Processor information
* User-related directories

Programs and scripts can use these variables instead of relying on hard-coded paths.

---

## The System32 Folder

A critical Windows system directory is:

```text
C:\Windows\System32
```

System32 contains:

* Important Windows components
* System libraries
* Administrative tools
* Executable files required by the operating system

Files in System32 should not be deleted or modified without understanding exactly what they do, because damaging this directory can make Windows unstable or unusable.

---

## Windows User Accounts

Windows local accounts are commonly divided into two broad account types:

* Administrator
* Standard User

### Administrator

An Administrator can perform system-level actions such as:

* Manage local users
* Manage groups
* Change system settings
* Install software
* Perform administrative tasks

### Standard User

A Standard User normally works with their own files and settings but has limited permission to make system-wide changes.

| Account type  | General access                                        |
| ------------- | ----------------------------------------------------- |
| Administrator | System-wide administrative control                    |
| Standard User | Limited access focused on personal files and settings |

Using a Standard User account for ordinary activity reduces the damage that mistakes or malicious software may cause.

---

## User Profiles

A user account provides an identity for signing in.

A user profile stores that account’s personal files and settings.

Windows user profiles are commonly stored under:

```text
C:\Users
```

Example:

```text
C:\Users\Max
```

A profile is normally created when the user signs in for the first time.

Common profile folders include:

* Desktop
* Documents
* Downloads
* Music
* Pictures

---

## Local Users and Groups

The Local Users and Groups management console can be opened with:

```text
lusrmgr.msc
```

It contains two major sections:

* Users
* Groups

### Users

The Users section lists local accounts on the computer.

### Groups

Groups collect permissions and administrative abilities.

When a user is added to a group, that user receives the permissions associated with the group.

A user may belong to multiple groups.

```text
User joins group
      ↓
User inherits group permissions
```

---

## User Account Control

User Account Control, or UAC, helps prevent unauthorized system-level changes.

When a program attempts an administrative action, Windows may display a confirmation or credential prompt.

UAC helps separate:

* Normal user activity
* Administrative actions

Its purpose is to make unexpected or unauthorized system changes more difficult.

```text
UAC = confirmation layer for administrative changes
```

UAC is not a replacement for antivirus protection or careful security practices, but it adds an important barrier.

---

## Windows Settings and Control Panel

Windows provides more than one interface for managing system configuration.

### Settings

The Settings application is the main modern interface for many common Windows options.

It includes areas related to:

* System configuration
* Devices
* Networking
* Accounts
* Privacy
* Security
* Applications
* Updates

### Control Panel

Control Panel is the older Windows configuration interface.

It still contains administrative and advanced options that may not be fully represented in the Settings application.

The location and appearance of particular options can vary between Windows versions, so the important skill is understanding the purpose of the tools rather than memorizing one exact menu path.

---

## Task Manager

Task Manager provides information about running applications, processes, system performance, users, and startup programs.

It can be used to:

* View running applications
* Inspect background processes
* Monitor CPU usage
* Monitor memory usage
* Monitor disk and network activity
* End unresponsive tasks
* Review startup applications
* View signed-in users and active sessions

### Important caution

Ending an unfamiliar process can cause an application or Windows feature to stop working. A process should not be terminated unless its purpose is understood.

---

## Important Terms

| Term          | Meaning                                              |
| ------------- | ---------------------------------------------------- |
| RDP           | Protocol used for graphical remote access to Windows |
| NTFS          | Modern Windows file system                           |
| Journaling    | Recording file-system changes for recovery           |
| EFS           | Windows file encryption feature                      |
| ADS           | Additional data stream attached to an NTFS file      |
| `%windir%`    | Environment variable for the Windows directory       |
| System32      | Directory containing critical Windows components     |
| Administrator | Account with system-level permissions                |
| Standard User | Account with limited permissions                     |
| User profile  | Personal files and settings belonging to a user      |
| Group         | Collection of permissions assigned to users          |
| `lusrmgr.msc` | Local Users and Groups management console            |
| UAC           | Security prompt for administrative actions           |
| Task Manager  | Tool for viewing processes and system performance    |

---

## Key Takeaway

Today I completed Windows Fundamentals 1 and reviewed the main components of a Windows system.

I learned how RDP provides graphical access to a remote Windows machine, how NTFS stores and protects files, how permissions control access, and how ADS can store additional data.

I also reviewed critical Windows directories, environment variables, user accounts, profiles, groups, UAC, system configuration tools, and Task Manager.

Some of the room’s interface instructions were based on older Windows versions, so I focused on the underlying Windows concepts rather than documenting menu paths that may no longer match current systems.
