# Day 16 - Windows CLI Basics, WSL, and System Enumeration

## Rooms Completed
- Windows CLI Basics

---

# Main Learning Objectives

Today focused on:
- Windows Command Prompt (CMD)
- Filesystem navigation
- System enumeration
- Network information gathering
- Windows vs Linux CLI comparison
- WSL (Windows Subsystem for Linux)
- Administrator privileges and permissions

This was an important foundational operating systems and command-line day.

---

# What Is CMD?

CMD (Command Prompt) is:
- a Windows shell/interpreter
- a text-based interface for interacting with Windows

Instead of clicking:
- folders
- menus
- windows

we type commands directly into the shell.

Learned that:
- terminal = interface/window
- shell = command interpreter

Examples:
- Bash = Linux shell
- CMD = Windows shell
- PowerShell = advanced Windows shell

---

# Windows Filesystem Navigation

## Show Current Directory

```cmd
cd
```

Purpose:
- display current location/path

Linux equivalent:

```bash
pwd
```

---

## List Files and Folders

```cmd
dir
```

Purpose:
- list files and directories

Linux equivalent:

```bash
ls
```

---

## Show Hidden Files and Folders

```cmd
dir /a
```

Purpose:
- show all files and folders, including hidden ones

Linux equivalent:

```bash
ls -al
```

Learned:
- hidden files are not necessarily secret
- hidden files in Linux usually start with a dot, like `.bashrc`
- attackers and analysts both inspect hidden files

---

## Change Directory

```cmd
cd foldername
```

Purpose:
- move into another folder

Linux equivalent:

```bash
cd foldername
```

---

## Move To Parent Directory

```cmd
cd ..
```

Purpose:
- move to parent directory

Linux equivalent:

```bash
cd ..
```

Learned:
- ".." means parent directory
- cd = change directory
- cd .. = change to parent directory

---

## Clear Screen

```cmd
cls
```

Purpose:
- clear terminal screen

Linux equivalent:

```bash
clear
```

---

## Read File Contents

```cmd
type filename.txt
```

Purpose:
- display file contents inside terminal

Linux equivalent:

```bash
cat filename.txt
```

---

## Search Recursively For Files

```cmd
dir /s filename.txt
```

Purpose:
- search subdirectories recursively

Linux equivalent:

```bash
find . -name filename.txt
```

Learned:
- recursive searching is important in investigations and enumeration

---

# System Enumeration Commands

Enumeration means:
- gathering information about a system

One of the most important concepts in cybersecurity.

---

## Current Logged-In User

```cmd
whoami
```

Purpose:
- identify current user account

Learned:
- attackers and analysts often run this immediately
- permissions depend on current user

Linux equivalent:

```bash
whoami
```

---

## Computer Hostname

```cmd
hostname
```

Purpose:
- identify computer name on network

Learned:
- machine names can reveal role or department
- important in enterprise environments

Linux equivalent:

```bash
hostname
```

---

## Windows System Information

```cmd
systeminfo
```

Purpose:
- display:
  - OS version
  - architecture
  - hardware information
  - patch/build details

Important fields:
- OS Name
- OS Version
- System Type

Linux equivalents:

```bash
uname -a
```

```bash
hostnamectl
```

---

## Network Configuration

```cmd
ipconfig
```

Purpose:
- display network settings

Learned about:
- IPv4 address
- default gateway
- local/private IP addresses

Linux equivalents:

```bash
ip a
```

or:

```bash
ifconfig
```

---

# Extended Learning - Windows vs Linux CLI

## Major Similarities Learned

| Linux | Windows CMD | Purpose |
|---|---|---|
| ls | dir | List files |
| cat | type | Read files |
| clear | cls | Clear screen |
| pwd | cd | Show current location |
| cd | cd | Change directory |
| whoami | whoami | Current user |
| hostname | hostname | Computer name |

---

# Important Filesystem Differences

## Linux Path Separator

```bash
/
```

Example:

```bash
/home/willj/Documents
```

---

## Windows Path Separator

```cmd
\
```

Example:

```cmd
C:\Users\willj\Documents
```

---

# Linux Directory Symbols

## Current Directory

```bash
.
```

## Parent Directory

```bash
..
```

## Home Directory

```bash
~
```

---

# WSL Observation

Learned that WSL allows Linux to access Windows filesystems.

Example:

Windows:
```cmd
C:\Users\willj
```

appears inside Linux as:

```bash
/mnt/c/Users/willj
```

Observed differences between:
- Linux home directory (`~`)
- Windows filesystem paths exposed inside WSL

Did not yet study:
- manual mounting commands
- Linux filesystem management

---

# Administrator Privileges

## Learned Difference Between:

### Normal CMD

```cmd
C:\Users\willj>
```

and:

### Administrator CMD

```cmd
Administrator: Command Prompt
C:\Windows\System32>
```

---

# Principle of Least Privilege

Important cybersecurity concept:
- only use admin/root privileges when necessary

Why:
- safer
- reduces accidental damage
- limits malware capabilities

---

# Learned About sudo

Linux:

```bash
sudo command
```

Windows equivalent:
- Run CMD as Administrator

Interesting finding:
- newer Windows versions now include experimental sudo support
- sudo was disabled on current machine

---

# File vs Folder Deletion

## Delete Files

```cmd
del filename.txt
```

## Delete Directories/Folders

```cmd
rmdir foldername
```

or:

```cmd
rd foldername
```

Learned:
- del targets files
- rmdir/rd targets directories

Linux equivalents:

## Delete Files

```bash
rm filename.txt
```

## Delete Directories

```bash
rm -r foldername
```

---

# Additional Linux Commands Reviewed

## Show Current Directory

```bash
pwd
```

---

## List Files

```bash
ls
```

---

## Show Hidden Files

```bash
ls -al
```

---

## Change Directory

```bash
cd foldername
```

---

## Move To Parent Directory

```bash
cd ..
```

---

## Move To Home Directory

```bash
cd ~
```

---

## Read File Contents

```bash
cat filename.txt
```

---

## Clear Terminal

```bash
clear
```

---

# Practical Exercises Performed

## On TryHackMe VM
- Navigated filesystem using CMD
- Listed hidden files
- Searched for task_brief.txt
- Read file contents
- Gathered system information
- Gathered network information

---

# On Personal Windows Laptop

## CMD Practice
- Opened normal CMD
- Opened Administrator CMD
- Compared normal vs elevated privileges
- Created test directories
- Deleted test files/folders
- Tested del command behavior
- Tested rmdir behavior
- Practiced cd .. navigation

---

# WSL/Linux Practice
- Opened Ubuntu terminal
- Compared:
```bash
~
```

vs:

```bash
/mnt/c/Users/willj
```

- Practiced Linux navigation commands
- Compared Linux and Windows command syntax
- Used pwd to inspect current path

---

# Cybersecurity Concepts Reinforced

- Enumeration
- User permissions
- Administrator/root privileges
- Filesystem structure
- Hidden files
- Network identification
- Local IP addressing
- System identification
- Terminal usage
- Shell behavior
- Principle of least privilege

---

# Important Realizations

- Linux and Windows share many CLI concepts
- Cybersecurity heavily relies on system enumeration
- CLI tools provide faster and more precise control than GUI
- Understanding operating systems is foundational before advanced hacking concepts
- Attackers and defenders both use enumeration commands

---

# Overall Reflection

Today was one of the most important foundational operating systems and command-line learning days so far.

The focus was not only memorizing commands, but understanding:
- how systems are structured
- how users interact with operating systems
- how permissions work
- how analysts gather information
- how Linux and Windows compare internally

Extended experimentation on personal Windows CMD and WSL environments helped reinforce concepts beyond the TryHackMe room itself.
