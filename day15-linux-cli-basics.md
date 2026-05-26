# Day 15 - Linux CLI Basics

## Overview
Today I completed the Linux CLI Basics room in TryHackMe and practiced both inside the TryHackMe virtual machine and my own Linux terminal environment using Bash through Windows Terminal and WSL.

This room focused on learning how to interact directly with the Linux operating system using the command-line interface (CLI), navigate the Linux filesystem, locate files, retrieve system information, and understand the foundations of Linux terminal usage in cybersecurity.

---

# Topics Covered

# Introduction to Linux CLI

## CLI (Command Line Interface)
The CLI allows users to interact with the operating system by typing commands directly into the terminal rather than using a graphical interface.

## Terminal
The terminal is the application window/interface used to type Linux commands.

Examples:
- Ubuntu Terminal
- Windows Terminal

## Shell
A shell is a command interpreter that reads commands entered by the user and communicates with the operating system to execute them.

## Bash
Bash (Bourne Again Shell) is the most common Linux shell.

## Extended Learning
- Learned the difference between terminal and shell
- Learned that Windows Terminal hosts shells such as Bash and PowerShell
- Learned that Bash interprets commands and acts as an interface between the user and the operating system

---

# Linux Filesystem Navigation

## Linux Root Directory
Linux starts from the root directory:

/

Everything branches from this location.

## Important Linux Directories

| Directory | Purpose |
|---|---|
| / | Root filesystem |
| /home | User home directories |
| /etc | Configuration files |
| /var | Logs and variable data |
| /tmp | Temporary files |

## Important Symbols

| Symbol | Meaning |
|---|---|
| ~ | Home directory |
| / | Root filesystem |
| . | Current directory |
| .. | Parent directory |

## Extended Learning
- Learned that Linux uses forward slashes "/" instead of Windows backslashes "\"
- Learned that Linux is case-sensitive
- Learned that Linux paths are exact and literal

---

# Basic Linux Navigation Commands

## pwd
Print Working Directory

Displays the current location in the filesystem.

Example:
pwd

## ls
Lists files and directories inside the current directory.

Example:
ls

## ls -l
Displays detailed information about files and directories.

Includes:
- Permissions
- Ownership
- File sizes
- Modification dates

## ls -al
Displays all files including hidden files in detailed format.

## cd
Change Directory

Used to move between directories.

Examples:
cd Documents
cd ..
cd ~
cd /

## Extended Learning
- Learned that commands can accept arguments
- Learned that "cd Documents" means "change directory to Documents"
- Learned the difference between root "/" and home "~"

---

# Hidden Files in Linux

Linux hides files and directories beginning with a dot "."

Examples:
- .bashrc
- .ssh
- .git

## Extended Learning
- Learned that hidden files often contain configuration data
- Learned that Linux hides these files by default unless using ls -a or ls -al

---

# File Searching and Reading

## find Command
Used to recursively search for files and directories.

Example:
find ~ -name mission_brief.txt

Breakdown:
- find = search utility
- ~ = start from home directory
- -name = search by filename

## cat Command
Displays file contents directly in the terminal.

Example:
cat mission_brief.txt

## Extended Learning
- Learned that Linux recursively searches directories using find
- Learned that many Linux configuration and information files are plain text files

---

# System Enumeration and Information Gathering

## whoami
Displays the current logged-in user.

Example:
whoami

## uname -a
Displays detailed system and kernel information.

Example:
uname -a

Information gathered:
- Kernel type
- Hostname
- Kernel version
- System architecture

## df -h
Displays disk usage in human-readable format.

Example:
df -h

## Extended Learning
- Learned that enumeration means gathering information about a system
- Learned that system enumeration is foundational in cybersecurity and system administration
- Learned the difference between Linux kernel and Linux distribution

---

# Linux Distribution Information

## /etc Directory
Contains important Linux system configuration files.

## os-release File
Used to identify Linux distribution details.

Example:
cat os-release

Information gathered:
- Ubuntu version
- Distribution name
- Release codename
- LTS release information

## Extended Learning
- Learned that Linux stores many system settings in text-based configuration files
- Learned that Ubuntu LTS stands for Long Term Support

---

# TryHackMe Practical Exercises Performed

During the TryHackMe virtual lab, I:

- Opened and used the Linux terminal
- Used pwd to determine current location
- Used ls, ls -l, and ls -al to inspect directories
- Navigated directories using cd
- Used cd .. to move to parent directories
- Used cd ~ to return to the home directory
- Explored Linux filesystem structure
- Located mission_brief.txt using find
- Navigated to hidden directories
- Used cat to read mission_brief.txt
- Gathered system information using whoami
- Retrieved kernel and architecture information using uname -a
- Checked disk usage using df -h
- Navigated to /etc
- Read os-release to identify Linux distribution
- Located and opened day1_report.txt independently

---

# Practice Performed on My Own Linux Terminal

Using Bash through Windows Terminal and WSL, I practiced:

- pwd
- ls
- ls -l
- cd
- cd ..
- cd ~
- cd /
- Navigating into /var and /home
- Understanding Linux prompts
- Understanding path differences between Windows and Linux
- Troubleshooting command syntax issues
- Understanding shell behavior and command interpretation
- Understanding why empty directories return no output with ls
- Understanding the difference between executing a file versus navigating to a directory

---

# Important Cybersecurity Concepts Learned

- Linux CLI navigation
- Filesystem hierarchy
- System enumeration
- Recursive file searching
- Hidden files and configuration files
- Kernel identification
- Distribution fingerprinting
- Command interpretation by shells
- Bash shell fundamentals
- Human-readable disk usage analysis
- Linux permissions awareness
- Terminal workflow thinking

---

# Important Linux Commands Learned

| Command | Purpose |
|---|---|
| pwd | Show current directory |
| ls | List directory contents |
| ls -l | Detailed directory listing |
| ls -al | Show hidden files with details |
| cd | Change directory |
| find | Search for files |
| cat | Display file contents |
| whoami | Show current user |
| uname -a | Show system information |
| df -h | Show disk usage |

---

# Important Linux Concepts Learned

| Concept | Meaning |
|---|---|
| CLI | Command Line Interface |
| Terminal | Interface window for commands |
| Shell | Command interpreter |
| Bash | Common Linux shell |
| Kernel | Core of operating system |
| Distribution | Linux OS package such as Ubuntu |
| Enumeration | Gathering system information |

---

# Key Takeaway

Linux command-line interaction may initially seem intimidating, but it provides direct, powerful, and precise control over the operating system. Understanding Linux CLI fundamentals is essential for cybersecurity, system administration, troubleshooting, and working with real-world technical environments.
