# Day 29 – Linux Fundamentals Part 3

## TryHackMe Room

Linux Fundamentals Part 3

---

## Topics Covered

* Terminal text editors
* Downloading files from the web
* Securely transferring files between computers
* Hosting a temporary Python web server
* Viewing and managing running processes
* Managing system services
* Foreground and background processes
* Scheduling automated tasks with cron
* Managing packages and software repositories
* Understanding Linux system and application logs

---

## Terminal Text Editors

### Nano

Nano is a beginner-friendly terminal text editor used to create and modify text files.

```bash
nano myfile
```

This opens `myfile` if it exists or creates it if it does not.

### Nano Shortcuts

| Shortcut   | Purpose                          |
| ---------- | -------------------------------- |
| `Ctrl + O` | Save the file                    |
| `Ctrl + X` | Exit Nano                        |
| `Ctrl + W` | Search for text                  |
| `Ctrl + K` | Cut text                         |
| `Ctrl + U` | Paste text                       |
| `Ctrl + C` | Show the current cursor position |
| `Ctrl + _` | Jump to a line                   |
| `Alt + U`  | Undo                             |
| `Alt + E`  | Redo                             |
| `Alt + 6`  | Copy text                        |

### VIM

VIM is a more advanced terminal text editor.

Its benefits include:

* Customizable keyboard shortcuts
* Syntax highlighting
* Availability on systems where Nano may not be installed
* Strong support for coding and software development

---

## Downloading Files with Wget

The `wget` command downloads files from a web address.

```bash
wget https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt
```

The downloaded file is saved in the current directory.

---

## Secure File Transfers with SCP

SCP stands for Secure Copy.

It transfers files between computers using SSH for authentication and encryption.

### Copy a Local File to a Remote Computer

```bash
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```

This sends the local file `important.txt` to the remote computer and saves it as `transferred.txt`.

### Copy a Remote File to the Local Computer

```bash
scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt
```

This retrieves `documents.txt` from the remote computer and saves it locally as `notes.txt`.

---

## Hosting Files with Python

Python can create a temporary web server in the current directory.

```bash
python3 -m http.server
```

The server normally runs on port `8000`.

A file can then be downloaded from another terminal or computer using:

```bash
wget http://10.64.141.225:8000/myfile
```

The terminal running the Python server must remain open while the file is being served.

---

## Linux Processes

A process is a program or command currently running on the system.

Each process receives a Process ID called a PID.

### Viewing Processes

```bash
ps
```

Shows processes associated with the current terminal session.

```bash
ps aux
```

Shows detailed processes across the wider system, including processes owned by other users and system processes.

```bash
top
```

Shows a continuously updating view of processes, CPU usage and memory usage.

---

## Managing Processes

The `kill` command sends a signal to a process using its PID.

```bash
kill 1337
```

By default, this sends `SIGTERM`, which asks the process to shut down cleanly.

### Process Signals

| Signal    | Meaning                           |
| --------- | --------------------------------- |
| `SIGTERM` | Terminate the process cleanly     |
| `SIGKILL` | Terminate the process immediately |
| `SIGSTOP` | Pause or suspend the process      |

Examples:

```bash
kill -SIGTERM 1337
```

```bash
kill -SIGKILL 1337
```

```bash
kill -SIGSTOP 1337
```

---

## Namespaces

A namespace isolates processes by giving them their own view of parts of the Linux system.

Namespaces can separate:

* Process IDs
* Network resources
* Users
* Filesystems
* System resources

This isolation improves security by preventing processes in different namespaces from automatically seeing or interfering with one another.

---

## Parent and Child Processes

A process that starts another process is called a parent process.

The new process is called a child process.

Ubuntu uses `systemd` to manage many services and processes started by the system.

---

## Managing Services with Systemctl

The `systemctl` command manages services controlled by `systemd`.

### Start a Service

```bash
systemctl start apache2
```

### Stop a Service

```bash
systemctl stop apache2
```

### Enable a Service at Boot

```bash
systemctl enable apache2
```

### Disable a Service at Boot

```bash
systemctl disable apache2
```

### Check a Service’s Status

```bash
systemctl status apache2
```

`start` runs the service immediately, while `enable` configures it to start automatically when the system boots.

---

## Foreground and Background Processes

A foreground process controls the current terminal until it finishes or is suspended.

Adding `&` starts a command in the background.

```bash
echo "Hi THM" &
```

Pressing:

```text
Ctrl + Z
```

suspends the current foreground process.

The `fg` command returns a suspended or background job to the foreground.

```bash
fg
```

---

## Automating Tasks with Cron

Cron runs commands automatically according to a schedule.

A cron job is one scheduled task, while a crontab is the file containing the schedules and commands.

Edit the current user’s crontab with:

```bash
crontab -e
```

### Crontab Format

```text
MIN HOUR DOM MON DOW CMD
```

| Field  | Meaning            |
| ------ | ------------------ |
| `MIN`  | Minute             |
| `HOUR` | Hour               |
| `DOM`  | Day of the month   |
| `MON`  | Month              |
| `DOW`  | Day of the week    |
| `CMD`  | Command to execute |

### Backup Example

```bash
0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/
```

This copies the `Documents` directory to `/var/backups/` every 12 hours.

The asterisk `*` means every possible value for that field.

---

## Linux Package Management

A package contains the files needed to install and run software.

A repository is an online source containing software packages.

APT is Ubuntu’s package-management system.

### Refresh Package Information

```bash
apt update
```

This checks configured repositories and refreshes the local package information.

### Install Software

```bash
apt install sublime-text
```

### Remove Software

```bash
apt remove sublime-text
```

---

## Adding Software Repositories

Additional repositories allow APT to install software that is not available in Ubuntu’s default repositories.

Third-party repository files are commonly stored in:

```text
/etc/apt/sources.list.d/
```

Repositories can also be managed using:

```bash
add-apt-repository
```

A repository can be removed with:

```bash
add-apt-repository --remove ppa:PPA_Name/ppa
```

---

## GPG Keys

GPG keys help verify that software came from the expected developer and has not been improperly altered.

The room demonstrated downloading and adding a GPG key with:

```bash
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```

The pipe `|` sends the output of `wget` into the next command.

---

## Linux Logs

Linux commonly stores system and application logs inside:

```text
/var/log
```

Logs record activity involving:

* The operating system
* Applications
* Services
* Authentication attempts
* Network connections
* Errors
* Security events

### Services Discussed

* Apache2 web server
* Fail2ban brute-force monitoring service
* UFW firewall

### Access Logs

Access logs record requests made to a service, such as a web server.

They can help identify:

* Requested resources
* Request times
* Request sources
* Successful and unsuccessful requests

### Error Logs

Error logs record failures and problems involving a service or application.

They are useful for diagnosing:

* Missing files
* Configuration problems
* Failed requests
* Application errors

### Log Rotation

Log rotation automatically manages older logs so that individual log files do not continue growing forever.

---

## Commands Learned and Practised

| Command                       | Purpose                                        |
| ----------------------------- | ---------------------------------------------- |
| `nano filename`               | Create or edit a file using Nano               |
| `wget URL`                    | Download a file from a web address             |
| `scp SOURCE DESTINATION`      | Securely copy files between computers          |
| `python3 -m http.server`      | Start a temporary web server                   |
| `ps`                          | View processes in the current terminal session |
| `ps aux`                      | View detailed system-wide processes            |
| `top`                         | View processes and resource usage in real time |
| `kill PID`                    | Send `SIGTERM` to a process                    |
| `kill -SIGTERM PID`           | Request a clean process shutdown               |
| `kill -SIGKILL PID`           | Force a process to terminate immediately       |
| `kill -SIGSTOP PID`           | Pause a process                                |
| `systemctl start SERVICE`     | Start a service                                |
| `systemctl stop SERVICE`      | Stop a service                                 |
| `systemctl enable SERVICE`    | Start a service automatically during boot      |
| `systemctl disable SERVICE`   | Prevent a service from starting during boot    |
| `systemctl status SERVICE`    | Check the status of a service                  |
| `command &`                   | Start a command in the background              |
| `Ctrl + Z`                    | Suspend a foreground process                   |
| `fg`                          | Return a job to the foreground                 |
| `crontab -e`                  | Edit scheduled cron jobs                       |
| `apt update`                  | Refresh package information                    |
| `apt install PACKAGE`         | Install a software package                     |
| `apt remove PACKAGE`          | Remove a software package                      |
| `add-apt-repository`          | Add a software repository                      |
| `add-apt-repository --remove` | Remove a software repository                   |

---

## Key Takeaway

Today I completed Linux Fundamentals Part 3 and finished the Linux Fundamentals module. I learned how to edit files from the terminal, transfer and serve files, view and control processes, manage system services, automate recurring tasks, install software through repositories and investigate system activity through logs. These skills provide a stronger Linux foundation for future penetration testing and offensive-security labs.
