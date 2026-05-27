# Day 16 - Windows CLI Basics

## Rooms Completed
- Windows CLI Basics

---

# Topics Learned

## Windows Command Prompt (CMD)
- Learned what CMD (Command Prompt) is
- Learned that CMD is a shell/interpreter for Windows commands
- Learned difference between terminal and shell
- Compared CMD with Linux Bash
- Learned why cybersecurity professionals use CLI tools

---

# Windows Filesystem Navigation

## Commands Learned

### Show current directory
```cmd
cd
```

### List files and folders
```cmd
dir
```

### Show hidden files and folders
```cmd
dir /a
```

### Change directory
```cmd
cd foldername
```

### Move back to parent directory
```cmd
cd ..
```

### Clear terminal screen
```cmd
cls
```

### Read file contents
```cmd
type filename.txt
```

### Search for files recursively
```cmd
dir /s filename.txt
```

---

# System Enumeration Commands

## Current logged-in user
```cmd
whoami
```

## Computer hostname
```cmd
hostname
```

## Windows system information
```cmd
systeminfo
```

## Network configuration
```cmd
ipconfig
```

---

# Linux vs Windows CLI Comparison

| Linux | Windows CMD | Purpose |
|---|---|---|
| ls | dir | List files |
| cat | type | Read file |
| clear | cls | Clear screen |
| pwd | cd | Show current location |
| / | \ | Path separator |
| ifconfig/ip a | ipconfig | Network information |

---

# Concepts Learned

- Terminal vs shell
- CMD vs PowerShell
- Filesystem navigation
- Parent directory
- Hidden files and folders
- System enumeration
- User permissions
- Administrator privileges
- Windows filesystem structure
- Linux and Windows command similarities
- Principle of least privilege
- Difference between deleting files and folders
- Difference between normal CMD and Administrator CMD

---

# WSL (Windows Subsystem for Linux)

## Learned:
- WSL allows Linux inside Windows
- Linux filesystem uses:
```bash
/home/username
```

- Windows drives are mounted in Linux as:
```bash
/mnt/c
```

- Difference between:
```bash
~
```
(home directory)

and:

```bash
/mnt/c/Users/username
```
(Windows filesystem mounted inside Linux)

---

# Additional Linux Commands Reviewed

## Current location
```bash
pwd
```

## List files
```bash
ls
```

## Change directory
```bash
cd
```

## Parent directory
```bash
cd ..
```

## Home directory
```bash
cd ~
```

## Read file contents
```bash
cat filename.txt
```

---

# Practical Exercises Performed

## On TryHackMe VM
- Navigated directories using CMD
- Listed hidden files
- Searched for task_brief.txt
- Read file contents using type
- Gathered system information
- Gathered network information

---

# Personal Practice On Own Laptop

## Windows CMD Practice
- Opened normal CMD
- Opened Administrator CMD
- Practiced directory navigation
- Created and deleted test folders
- Tested file deletion commands
- Learned difference between:
```cmd
del
```
and:
```cmd
rmdir
```

- Explored system32 directory carefully
- Tested sudo command behavior on Windows

---

# Linux/WSL Practice
- Opened Ubuntu terminal
- Used WSL environment
- Compared Linux home directory vs mounted Windows filesystem
- Practiced Linux navigation commands
- Used pwd to inspect current location
- Practiced cd ~ and cd ..

---

# Key Cybersecurity Takeaways

- Enumeration is one of the first steps in cybersecurity investigations
- CLI tools provide faster and more precise control than GUI
- Permissions and privilege levels are critical in operating systems
- Attackers and defenders both use enumeration commands
- Understanding filesystems is foundational for cybersecurity
- Linux and Windows share many similar command-line concepts

---

# Overall Reflection

Today helped strengthen understanding of:
- Windows command line basics
- Linux vs Windows CLI similarities
- Filesystem navigation
- System information gathering
- Administrator privileges
- WSL/Linux integration inside Windows

This was an important foundational operating systems and command-line learning day.
