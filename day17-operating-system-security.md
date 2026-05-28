# Day 17 – Operating System Security & Linux User Management

## TryHackMe Room

Operating System Security

---

# Topics Covered

## Operating System Security Fundamentals

* Learned that the operating system acts as the layer between hardware and applications

* Reviewed how operating systems manage:

  * users
  * permissions
  * authentication
  * hardware access
  * security controls

* Learned the importance of protecting:

  * confidentiality
  * integrity
  * availability (CIA Triad)

---

# CIA Triad

## Confidentiality

* Preventing unauthorized access to private data
* Examples:

  * passwords
  * personal files
  * banking information

## Integrity

* Ensuring data is not modified improperly
* Examples:

  * file tampering
  * altered logs
  * unauthorized changes

## Availability

* Keeping systems and data accessible
* Examples:

  * ransomware
  * DDoS attacks
  * service outages

---

# Common Operating System Security Weaknesses

## Weak Passwords

* Learned how attackers exploit:

  * common passwords
  * reused passwords
  * predictable passwords

* Reviewed examples of commonly used passwords:

  * 123456
  * password
  * qwerty

---

# Authentication Factors

Learned the 3 authentication factors:

### Something You Know

* password
* PIN

### Something You Are

* fingerprint
* face recognition

### Something You Have

* phone authentication
* hardware token

---

# Password Attack Types

## Brute Force Attack

* Attempts all possible password combinations

## Dictionary Attack

* Uses lists of common passwords and leaked credentials

## Hybrid Attack

* Combines dictionary words with variations

## Credential Stuffing

* Uses leaked username/password combinations on multiple sites

---

# Principle of Least Privilege

* Users should only have the minimum permissions necessary
* Important security concept in Linux and cybersecurity

---

# Malware Concepts

## Trojan Horse

* Malicious software disguised as legitimate software

## Ransomware

* Encrypts files and demands payment for decryption

---

# Linux Authentication & Remote Access

## SSH (Secure Shell)

Learned how SSH allows secure remote login to another machine.

### SSH Syntax

```bash
ssh username@IP
```

Example:

```bash
ssh sammie@192.168.1.55
```

* username = account name
* IP = target machine address

---

# SSH Security Concepts

* First SSH connection stores server fingerprint
* Learned basic purpose of SSH key verification
* Learned why Linux hides password input during login

---

# Linux User & Permission Concepts

## Root Account

* Linux super administrator account
* Has unrestricted system access

## Privilege Escalation

* Process of gaining higher-level permissions
* Example:

  * normal user → root access

## Sudo

* Temporarily executes commands with elevated privileges

---

# Commands Learned & Practiced

## User & Identity Commands

### Switch User

```bash
su - username
```

### Switch To Root User

```bash
su - root
```

### Become Root Using Sudo

```bash
sudo su
```

### Exit Current Shell

```bash
exit
```

---

# User Management Commands

### Create User

```bash
sudo adduser username
```

### Delete User

```bash
sudo deluser username
```

### Delete User & Home Directory

```bash
sudo deluser --remove-home username
```

---

# Sudo Commands

### Run Command As Administrator

```bash
sudo command
```

Example:

```bash
sudo apt update
```

### Show Sudo Permissions

```bash
sudo -l
```

---

# File & Directory Commands

### Create Empty File

```bash
touch filename
```

---

# History & Enumeration Commands

### Show Previously Executed Commands

```bash
history
```

---

# Networking Commands

### Show IP Address & Interfaces

```bash
ip a
```

### Show Network Configuration (Legacy Command)

```bash
ifconfig
```

---

# SSH Commands

### Connect To Remote Machine

```bash
ssh username@IP
```

Example:

```bash
ssh sammie@192.168.1.55
```

---

# SSH Service Commands

### Enable SSH At Boot

```bash
sudo systemctl enable ssh
```

---

# Shell & Session Concepts

Learned that:

* every terminal session runs inside a shell
* `su`, `ssh`, and `sudo su` create new shell layers
* `exit` closes the current shell/session layer

Example:

* local shell
* remote SSH shell
* root shell

---

# Linux Permissions Introduction

Learned that permissions control:

* who can read
* who can write
* who can execute

---

# Windows vs Linux User Management

Compared Linux commands with Windows equivalents:

| Linux   | Windows                  |
| ------- | ------------------------ |
| adduser | net user /add            |
| deluser | net user /delete         |
| sudo    | Administrator privileges |
| root    | Administrator            |

---

# Practical Hands-On Practice

## TryHackMe Machine

* Logged into Linux machine using SSH
* Practiced Linux enumeration commands
* Explored files and command history

## Personal Linux CLI Practice

* Created local Linux user account
* Switched between users
* Created and viewed files
* Practiced deleting users
* Practiced shell/session navigation
* Explored Linux permission listings
* Retrieved local IP address using:

  * `ip a`
  * `ifconfig`

---

# Important Concepts Learned

* Authentication vs authorization
* User accounts vs root/admin privileges
* Linux permission separation
* Remote access fundamentals
* Weak passwords are often easier to exploit than software vulnerabilities
* Human behavior is one of the largest attack surfaces in cybersecurity

---

# Key Takeaway

Today was my first deeper exposure to real Linux user management, authentication, shell sessions, SSH remote access, and permission separation. I learned how Linux organizes users, privileges, and remote connections, and how attackers often exploit weak credentials and poor operational security rather than “hacking” systems directly.
