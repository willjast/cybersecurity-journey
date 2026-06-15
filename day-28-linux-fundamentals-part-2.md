# Day 28 – Linux Fundamentals Part 2

## TryHackMe Room

Linux Fundamentals Part 2

---

# Topics Covered

## Secure Shell – SSH

* Learned that SSH stands for **Secure Shell**
* Learned that SSH is used to remotely connect to and control another Linux machine
* Learned that data sent through SSH is encrypted while travelling across a network
* Connected from the TryHackMe AttackBox to the deployed Linux machine
* Learned that commands entered after connecting through SSH run on the remote machine
* Learned that SSH passwords do not display characters, dots, or symbols while being typed

### SSH Command Structure

```bash
ssh username@IP-address
```

### Room Example

```bash
ssh tryhackme@10.67.168.49
```

The IP address must be replaced with the address assigned to the deployed lab machine.

---

# Flags, Switches, and Arguments

## Arguments

An argument provides additional information to a command.

Example:

```bash
touch note
```

* `touch` is the command
* `note` is the argument

Some commands require more than one argument.

Example:

```bash
cp note note2
```

* `note` is the original file
* `note2` is the new copy

## Flags and Switches

Flags and switches modify or extend the default behaviour of a command.

### Show Hidden Files

```bash
ls -a
```

The `-a` flag means **all** and displays hidden files and folders.

Hidden Linux files and folders begin with a period:

```text
.hiddenfolder
```

The long version of `-a` is:

```bash
ls --all
```

### Display Command Help

```bash
ls --help
```

The `--help` option displays available options and short explanations for a command.

### Open a Manual Page

```bash
man ls
```

The `man` command opens the manual page for another command.

Press:

```text
q
```

to exit the manual page.

---

# Filesystem Interaction

## Creating a File

```bash
touch note
```

The `touch` command creates a blank file.

## Creating a Directory

```bash
mkdir mydirectory
```

The `mkdir` command means **make directory** and creates a folder.

## Copying a File

```bash
cp note note2
```

The `cp` command copies the contents of `note` into a new file named `note2`.

The original file remains unchanged.

## Moving or Renaming a File

```bash
mv note2 note3
```

The `mv` command can move or rename a file or folder.

In this example, `note2` is renamed to `note3`.

A file can also be moved into a folder:

```bash
mv note folder1
```

## Removing a File

```bash
rm note
```

The `rm` command removes a file.

## Removing a Directory

```bash
rm -R mydirectory
```

The `-R` flag removes a directory recursively, including the files and folders inside it.

## Determining a File Type

```bash
file note
```

The `file` command identifies the actual type of a file.

Example output:

```text
note: ASCII text
```

Linux files do not require filename extensions, so the `file` command can help determine what a file actually contains.

---

# Linux Permissions

## Viewing Permissions

```bash
ls -lh
```

The `-l` flag displays a long listing containing permissions, ownership, file size, date, and filename.

The `-h` flag displays file sizes in a human-readable format.

Example:

```text
-rw-r--r-- 1 cmnatic cmnatic 0 Feb 19 10:37 file1
```

The important sections include:

```text
-rw-r--r--   cmnatic   cmnatic
permissions    owner      group
```

## File Type Indicator

The first character identifies the type of item:

```text
- = regular file
d = directory
```

The following nine characters represent permissions.

## Permission Groups

Permissions are divided into three groups:

```text
Owner | Group | Others
```

Example:

```text
rwx | r-x | r-x
```

The hyphens are not separators. A hyphen means that a specific permission is not granted.

## Permission Meanings

| Permission    | Symbol | Numeric Value |
| ------------- | -----: | ------------: |
| Read          |    `r` |             4 |
| Write         |    `w` |             2 |
| Execute       |    `x` |             1 |
| No permission |    `-` |             0 |

## Numeric Permission Calculations

```text
rwx = 4 + 2 + 1 = 7
rw- = 4 + 2     = 6
r-x = 4 + 1     = 5
r-- = 4         = 4
--- = 0         = 0
```

## Common Permission Examples

| Symbolic    | Numeric | Meaning                                                                  |
| ----------- | ------: | ------------------------------------------------------------------------ |
| `rwxrwxrwx` |   `777` | Everyone has full access                                                 |
| `rwxr-xr-x` |   `755` | Owner has full access; group and others can read and execute             |
| `rwxr-x---` |   `750` | Owner has full access; group can read and execute; others have no access |
| `rwx------` |   `700` | Only the owner has access                                                |
| `rw-r--r--` |   `644` | Owner can read and write; group and others can only read                 |

Example:

```text
rwx | r-x | r-x
 7  |  5  |  5
```

Therefore:

```text
rwxr-xr-x = 755
```

## Changing Permissions

```bash
chmod 750 system_overview.txt
```

This applies the following permissions:

```text
Owner:  rwx = 7
Group:  r-x = 5
Others: --- = 0
```

---

# Users and Groups

Linux permissions can assign different access rights to:

* The file owner
* Members of the file's group
* All other users

This allows several users to work with the same file while having different levels of access.

## Switching Users

```bash
su user2
```

The `su` command switches to another user account.

This normally requires the other user's password.

## Login-Style User Switch

```bash
su -l user2
```

The `-l` flag starts a login-style session and loads more of the new user's environment.

It also places the session in the new user's home directory.

The long form is:

```bash
su --login user2
```

### Difference

```text
su user2     → switches users but may remain in the current directory
su -l user2  → switches users and loads the new user's login environment
```

---

# Common Linux Directories

## `/etc`

The `/etc` directory stores system-wide configuration files.

Important examples:

| Location       | Purpose                                        |
| -------------- | ---------------------------------------------- |
| `/etc/passwd`  | Stores user-account information                |
| `/etc/shadow`  | Stores protected password hashes               |
| `/etc/sudoers` | Controls which users and groups may use `sudo` |

Important distinction:

```text
/etc/passwd → user-account information
/etc/shadow → protected password hashes
```

## `/var`

The `/var` directory stores variable data that changes while the system and its services are running.

Important example:

```text
/var/log
```

This directory stores system and application logs.

## `/root`

The `/root` directory is the home directory of the root user.

It is different from the filesystem root:

```text
/      → top of the entire filesystem
/root  → root user's home directory
```

## `/tmp`

The `/tmp` directory stores temporary files.

Ordinary users can normally create files there, making it useful during authorized penetration-testing labs for temporarily storing scripts or collected information.

---

# Commands and Flags Cheat Sheet

| Command or flag | Purpose                                           | Example                         |
| --------------- | ------------------------------------------------- | ------------------------------- |
| `ssh`           | Connect to a remote machine securely              | `ssh tryhackme@10.67.168.49`    |
| `ls -a`         | Show hidden files and folders                     | `ls -a`                         |
| `ls --all`      | Long version of `ls -a`                           | `ls --all`                      |
| `ls -lh`        | Show detailed information and readable file sizes | `ls -lh`                        |
| `--help`        | Display command options                           | `ls --help`                     |
| `man`           | Open a command's manual page                      | `man ls`                        |
| `q`             | Exit a manual page                                | `q`                             |
| `touch`         | Create a blank file                               | `touch note`                    |
| `mkdir`         | Create a directory                                | `mkdir mydirectory`             |
| `cp`            | Copy a file                                       | `cp note note2`                 |
| `mv`            | Move or rename a file or folder                   | `mv note2 note3`                |
| `rm`            | Remove a file                                     | `rm note`                       |
| `rm -R`         | Remove a directory and its contents               | `rm -R mydirectory`             |
| `file`          | Determine a file's type                           | `file note`                     |
| `su`            | Switch to another user                            | `su user2`                      |
| `su -l`         | Switch user with a login-style session            | `su -l user2`                   |
| `chmod`         | Change permissions                                | `chmod 750 system_overview.txt` |

---

# Key Takeaways

* SSH provides encrypted remote access to Linux machines
* Arguments provide information to commands
* Flags change or extend command behaviour
* Linux files do not require filename extensions
* `cp` copies a file, while `mv` moves or renames it
* `rm` removes files, while `rm -R` removes directories and their contents
* Permissions are divided into owner, group, and others
* Permission hyphens represent missing permissions and are not separators
* Numeric permissions are calculated separately for each group
* `/etc`, `/var`, `/root`, and `/tmp` serve different system purposes
* Command manuals and help pages remove the need to memorize every option

---

# Room Completed

Completed Linux Fundamentals Part 2 and strengthened my understanding of:

* SSH remote access
* Flags, switches, and arguments
* File and directory management
* Linux permissions
* Users and groups
* Common Linux directories
