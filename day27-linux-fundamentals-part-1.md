# Day 27 – Linux Fundamentals Part 1

## TryHackMe Path

Cyber Security 101

## TryHackMe Room

Linux Fundamentals Part 1

---

# Progress Update

Continued the **Cyber Security 101** learning path by studying the first room in the Linux Fundamentals series.

This room introduced Linux background concepts, terminal interaction, filesystem navigation, file searching, text searching, and basic shell operators.

I also practised the commands in an interactive Linux terminal.

---

# Topics Covered

## Background on Linux

Learned that Linux is used in many systems, including:

* Websites and web servers
* Car entertainment and control systems
* Point-of-sale systems
* Checkout registers
* Traffic-light controllers
* Industrial sensors
* Critical infrastructure

Linux is often lightweight and can run on systems with limited hardware resources.

Ubuntu Server can run on systems with approximately **512 MB of RAM**.

---

# Linux Distributions

Learned that Linux is an umbrella term for multiple Linux-based operating systems.

These different versions are called:

* Distributions
* Distros
* Flavours of Linux

Examples covered in the room:

* Ubuntu
* Debian

Ubuntu can be used as:

* A desktop operating system
* A server
* A web server
* A web application server

The Linux Fundamentals series uses Ubuntu.

---

# Open-Source Software

Learned that Linux is open-source.

This allows people and organizations to:

* View the source code
* Modify the source code
* Redistribute it
* Create Linux distributions for different purposes

---

# The Linux Terminal

Learned that many Linux systems do not have a graphical user interface installed.

Instead, users interact with the operating system through the terminal.

The terminal is text-based and accepts commands entered after the command prompt.

Example prompt:

```text
tryhackme@linux1:~$
```

Commands are entered after the `$` symbol.

---

# First Linux Commands

## `echo`

The `echo` command outputs text to the terminal.

Example:

```bash
echo Hello
```

Output:

```text
Hello
```

For text containing spaces, quotation marks can be used:

```bash
echo "Hello Friend!"
```

Output:

```text
Hello Friend!
```

---

## `whoami`

The `whoami` command displays the username of the currently logged-in account.

Example:

```bash
whoami
```

Possible output:

```text
tryhackme
```

---

# Interacting With the Filesystem

Learned commands for navigating the Linux filesystem and reading files.

| Command | Full name               | Purpose                               |
| ------- | ----------------------- | ------------------------------------- |
| `ls`    | Listing                 | Lists files and directories           |
| `cd`    | Change directory        | Moves into another directory          |
| `cat`   | Concatenate             | Displays the contents of a file       |
| `pwd`   | Print working directory | Shows the current full directory path |

---

# Listing Files With `ls`

The `ls` command shows the files and directories in the current location.

```bash
ls
```

Example output:

```text
Important Files
My Documents
Notes
Pictures
```

The contents of another directory can be listed without entering it:

```bash
ls Pictures
```

---

# Changing Directories With `cd`

The `cd` command changes the current working directory.

```bash
cd Pictures
```

After entering the directory, `ls` can be used again:

```bash
ls
```

Example output:

```text
dog_picture1.jpg
dog_picture2.jpg
dog_picture3.jpg
dog_picture4.jpg
```

A full directory path can also be used:

```bash
cd /home/ubuntu/Documents
```

---

# Reading Files With `cat`

The `cat` command displays the contents of a file directly in the terminal.

```bash
cat todo.txt
```

Example output:

```text
Here's something important for me to do later!
```

A file can also be read using its full path:

```bash
cat /home/ubuntu/Documents/todo.txt
```

This allows the file to be read without first moving into its directory.

---

# Finding the Current Location With `pwd`

The `pwd` command displays the full path of the current working directory.

```bash
pwd
```

Example output:

```text
/home/ubuntu/Documents
```

This shows exactly where the current directory is located within the Linux filesystem.

---

# Searching for Files

## `find`

The `find` command searches for files and directories.

To find a specific filename:

```bash
find -name passwords.txt
```

Example output:

```text
./folder1/passwords.txt
```

This means the file is inside `folder1`, below the current directory.

---

# Wildcard Searching

The asterisk `*` is a wildcard.

It represents any filename text.

To find every file ending in `.txt`:

```bash
find -name *.txt
```

Example output:

```text
./folder1/passwords.txt
./Documents/todo.txt
```

The pattern:

```text
*.txt
```

means any filename that ends with `.txt`.

---

# Counting Lines With `wc -l`

The `wc -l` command counts the number of lines in a file.

```bash
wc -l access.log
```

Example output:

```text
244 access.log
```

This means that `access.log` contains 244 lines.

---

# Searching Inside Files With `grep`

The `grep` command searches inside a file for matching text.

Example:

```bash
grep "81.143.211.90" access.log
```

This searches `access.log` and displays every line containing the specified IP address.

This is more efficient than manually reading hundreds of log entries.

---

# Recursive Searching With `grep -R`

The `-R` option tells `grep` to search recursively.

This means it searches:

* Files in the specified directory
* Files inside its subdirectories
* Additional directories below them

Example:

```bash
grep -R "PRETTY_NAME" /etc/
```

Example output:

```text
grep: /etc/sudoers: Permission denied
/etc/os-release:PRETTY_NAME="Ubuntu"
```

The result shows:

* The path of the matching file
* The line containing the matching text

A `Permission denied` message means the current account is not allowed to read that file.

---

# `find` Versus `grep`

| Command   | What it searches                              |
| --------- | --------------------------------------------- |
| `find`    | File and directory names                      |
| `grep`    | Text inside files                             |
| `grep -R` | Text across multiple files and subdirectories |

Simple comparison:

```text
find = Where is the file?
grep = Where is the text?
```

---

# Shell Operators

Learned that shell operators change how commands run or where their output goes.

| Operator | Purpose                                             |
| -------- | --------------------------------------------------- |
| `&`      | Runs a command in the background                    |
| `&&`     | Runs another command only if the first succeeds     |
| `>`      | Redirects output and replaces file contents         |
| `>>`     | Redirects output and adds to existing file contents |

---

# Background Operator `&`

The `&` operator runs a command in the background.

General format:

```bash
command &
```

This allows the terminal to remain available while the command continues running.

---

# Conditional Operator `&&`

The `&&` operator combines commands.

General format:

```bash
command1 && command2
```

The second command runs only when the first command finishes successfully.

```text
command1 succeeds
        ↓
command2 runs
```

If the first command fails, the second command does not run.

---

# Output Redirection With `>`

The `>` operator redirects command output into a file.

Example:

```bash
echo hey > welcome
```

This creates a file called `welcome` containing:

```text
hey
```

The file can be checked with:

```bash
cat welcome
```

Important:

If the file already exists, `>` overwrites its current contents.

---

# Appending Output With `>>`

The `>>` operator adds output to the end of a file without replacing its existing contents.

Example:

```bash
echo hello >> welcome
```

If `welcome` already contains:

```text
hey
```

It will then contain:

```text
hey
hello
```

---

# `>` Versus `>>`

| Operator | Effect on existing contents    |
| -------- | ------------------------------ |
| `>`      | Replaces them                  |
| `>>`     | Keeps them and adds new output |

Simple memory guide:

```text
>  = Write and replace
>> = Write and add
```

---

# Complete Command Chart

| Command                        | Purpose                               | Example                               |
| ------------------------------ | ------------------------------------- | ------------------------------------- |
| `echo`                         | Displays text in the terminal         | `echo Hello`                          |
| `echo`                         | Displays text containing spaces       | `echo "Hello Friend!"`                |
| `whoami`                       | Shows the current username            | `whoami`                              |
| `ls`                           | Lists files and directories           | `ls`                                  |
| `ls <directory>`               | Lists another directory's contents    | `ls Pictures`                         |
| `cd <directory>`               | Changes the current directory         | `cd Pictures`                         |
| `cd <path>`                    | Moves directly to a full path         | `cd /home/ubuntu/Documents`           |
| `cat <file>`                   | Displays file contents                | `cat todo.txt`                        |
| `cat <path>`                   | Reads a file using its full path      | `cat /home/ubuntu/Documents/todo.txt` |
| `pwd`                          | Shows the current full directory path | `pwd`                                 |
| `find -name <filename>`        | Finds a specific file                 | `find -name passwords.txt`            |
| `find -name *.txt`             | Finds all `.txt` files                | `find -name *.txt`                    |
| `wc -l <file>`                 | Counts lines in a file                | `wc -l access.log`                    |
| `grep "<text>" <file>`         | Searches for text inside one file     | `grep "81.143.211.90" access.log`     |
| `grep -R "<text>" <directory>` | Searches recursively across files     | `grep -R "PRETTY_NAME" /etc/`         |

---

# Shell Operator Chart

| Operator | Purpose                                       | Example                 |
| -------- | --------------------------------------------- | ----------------------- |
| `&`      | Runs a command in the background              | `command &`             |
| `&&`     | Runs the second command if the first succeeds | `command1 && command2`  |
| `>`      | Redirects output and overwrites a file        | `echo hey > welcome`    |
| `>>`     | Redirects output and appends to a file        | `echo hello >> welcome` |
| `*`      | Matches any filename text                     | `find -name *.txt`      |

---

# Quick Memory Guide

```text
echo     = Print text
whoami   = Which user am I?
ls       = What is here?
cd       = Move to another directory
cat      = Read this file
pwd      = Where am I?
find     = Where is the file?
wc -l    = How many lines?
grep     = Find text inside a file
grep -R  = Find text across many files
&        = Run in the background
&&       = Continue only if successful
>        = Write and replace
>>       = Write and add
*        = Match anything
```

---

# Practical Terminal Workflow

Practised the following command sequence:

```bash
whoami
pwd
ls
cd Documents
ls
cat todo.txt
find -name passwords.txt
find -name *.txt
wc -l access.log
grep "81.143.211.90" access.log
grep -R "PRETTY_NAME" /etc/
echo hey > welcome
echo hello >> welcome
cat welcome
```

The final `welcome` file contained:

```text
hey
hello
```

---

# Key Lessons

* Linux is widely used across servers, devices, shops, vehicles, and infrastructure.
* Linux distributions are different versions of Linux designed for different purposes.
* Ubuntu can be used as both a desktop operating system and a server.
* The terminal provides text-based control of a Linux system.
* `ls`, `cd`, `cat`, and `pwd` are essential filesystem commands.
* `find` searches for files and directories.
* `grep` searches for text inside files.
* `grep -R` searches recursively across several files and directories.
* `wc -l` counts file lines.
* `&` runs commands in the background.
* `&&` continues only after successful completion.
* `>` overwrites file contents.
* `>>` appends to file contents.
* The wildcard `*` matches any filename text.

---

# Room Progress

Studied the useful instructional tasks from the TryHackMe **Linux Fundamentals Part 1** room and completed practical work involving:

* Linux background concepts
* Terminal basics
* Filesystem navigation
* Reading files
* Searching for files
* Searching inside files
* Recursive searches
* Counting lines
* Shell operators
* Output redirection
