# Day 26 – Search Skills

## TryHackMe Path

Cyber Security 101

## TryHackMe Room

Search Skills

---

# Progress Update

Today marked the beginning of the **Cyber Security 101** learning path after completing the Pre Security path.

The Search Skills room focused on finding, evaluating, and verifying cybersecurity information using specialized search engines, vulnerability databases, official documentation, Linux manual pages, and GitHub repositories.

---

# Topics Covered

## Cybersecurity Search Skills

Learned that cybersecurity professionals do not need to memorize every command, vulnerability, or tool.

An important professional skill is knowing:

* What information is required
* Where to search for it
* How to narrow search results
* How to determine whether a source is trustworthy
* How to verify findings using multiple sources
* How to use information safely and legally

Search skills are important in both:

* Offensive security
* Defensive security
* Vulnerability research
* Threat intelligence
* Incident response
* Penetration testing
* Security troubleshooting

---

# Shodan

Learned that Shodan is a specialized search engine for publicly accessible internet-connected systems and services.

Unlike traditional search engines that primarily index webpages, Shodan gathers information from exposed network services.

Shodan can identify systems such as:

* Web servers
* Routers
* Firewalls
* VPN servers
* Remote-access services
* Internet of Things devices
* Traffic cameras
* Cloud systems
* Industrial control systems

## Service Banners

Learned that a banner is information returned by a network service.

A banner may reveal:

* IP address
* Open port
* Service type
* Software name
* Software version
* Hostname
* Organization
* Country
* Certificate information

Example:

```text
Server: Apache/2.4.1
```

A software banner may indicate the software version being used, but it does not automatically prove that the system is vulnerable.

The banner may be:

* Outdated
* Incorrect
* Incomplete
* Disguised
* Associated with software that has already been patched

## Shodan Filters

| Filter     | Purpose                                          | Example                 |
| ---------- | ------------------------------------------------ | ----------------------- |
| `country`  | Restricts results to a country                   | `country:CA`            |
| `port`     | Restricts results to a port                      | `port:22`               |
| `org`      | Searches within an organization or network owner | `org:"Example Company"` |
| `hostname` | Searches for a hostname or domain                | `hostname:example.com`  |

Example combined query:

```text
apache country:CA port:443
```

## Autonomous System Number

Learned that ASN stands for **Autonomous System Number**.

An ASN identifies a network or group of public IP address ranges operated under a common routing policy by an organization such as:

* An internet provider
* A cloud provider
* A university
* A government
* A large company

## Attack Surface

Learned that an external attack surface consists of publicly accessible systems and services that attackers may attempt to target.

Examples include:

* Websites
* Email servers
* VPN portals
* Remote Desktop services
* SSH servers
* Cloud servers
* Public databases

---

# VirusTotal

Learned that VirusTotal combines results from more than 70 antivirus engines and security scanners.

VirusTotal can investigate:

* Files
* URLs
* Domains
* IP addresses
* File hashes

It is commonly used by:

* SOC analysts
* Blue teams
* Malware analysts
* Incident responders
* Threat-intelligence researchers

## Detection Results

Example:

```text
55 / 70
```

This means that 55 security engines flagged the submitted item.

A large number of detections may strongly suggest malicious activity, but VirusTotal should not be treated as a final verdict.

Example:

```text
0 / 70
```

This means that none of the engines currently detected the item.

However:

> No detections does not prove that an item is safe.

New, targeted, or disguised malware may not yet be recognized.

## File Hashes

Learned that a file hash is a digital fingerprint calculated from a file’s contents.

Common hashing algorithms include:

* MD5
* SHA-1
* SHA-256

Searching a file hash allows an analyst to check whether VirusTotal has previously analyzed the exact file without necessarily uploading or executing it.

Two files can have the same filename but completely different hashes and contents.

## False Positive

A legitimate item is incorrectly identified as malicious.

## False Negative

A malicious item is incorrectly considered safe.

## Important VirusTotal Safety Rule

Confidential, personal, client, or company-sensitive files should not be uploaded to VirusTotal without authorization because submitted samples may become available to security researchers or service partners.

---

# CVE Vulnerability Databases

Learned that CVE stands for:

**Common Vulnerabilities and Exposures**

A CVE provides a standardized identifier for a publicly disclosed vulnerability.

Example format:

```text
CVE-YEAR-NUMBER
```

Example:

```text
CVE-2025-55182
```

## CVE Identifier Structure

| Section | Meaning                                 |
| ------- | --------------------------------------- |
| `CVE`   | Common Vulnerabilities and Exposures    |
| `2025`  | Year associated with the CVE assignment |
| `55182` | Unique sequence number                  |

The CVE number identifies the vulnerability but does not indicate its severity.

## Why CVEs Are Important

A CVE identifier allows the following groups to refer to the same vulnerability consistently:

* Software vendors
* Security researchers
* Vulnerability scanners
* Penetration testers
* Defensive security teams
* Government agencies
* Security documentation
* Patch-management systems

---

# CVSS

Learned that CVSS stands for:

**Common Vulnerability Scoring System**

CVSS measures the technical severity of a vulnerability using a score from `0.0` to `10.0`.

|    Score | Severity |
| -------: | -------- |
|      0.0 | None     |
|  0.1–3.9 | Low      |
|  4.0–6.9 | Medium   |
|  7.0–8.9 | High     |
| 9.0–10.0 | Critical |

CVSS considers factors such as:

* Attack location
* Attack complexity
* Required privileges
* Required user interaction
* Confidentiality impact
* Integrity impact
* Availability impact

## CVE Versus CVSS

```text
CVE  = Identifies the vulnerability
CVSS = Scores its technical severity
```

## Severity Versus Risk

Learned that a high CVSS score does not automatically make a vulnerability the highest priority for every organization.

Actual organizational risk also depends on:

* Whether the affected software is installed
* Whether the system is publicly exposed
* How important the affected asset is
* Whether exploitation is occurring in the wild
* Whether public exploit code exists
* Whether security controls reduce the risk
* Whether a patch or mitigation is available

---

# Proof of Concept

Learned that PoC stands for:

**Proof of Concept**

A PoC demonstrates that a vulnerability can be reproduced.

A PoC may consist of:

* A script
* A specially constructed request
* A test file
* A sequence of commands
* A technical explanation

A PoC is not always a complete exploit and may be:

* Incomplete
* Unreliable
* Version-specific
* Unsafe
* Incorrect
* Malicious

---

# Exploit-DB

Learned that Exploit-DB is a public database containing exploits and Proof-of-Concept material.

An Exploit-DB entry may contain:

* Vulnerable application
* Affected version
* Platform
* Exploit or PoC code
* Author
* Publication date
* Related CVE
* Exploit category

A public exploit or PoC does not provide permission to test systems without authorization.

---

# Official Technical Documentation

Learned that official product and tool documentation should normally be the first source checked when:

* Learning a tool
* Looking up syntax
* Understanding command options
* Configuring software
* Troubleshooting unexpected behaviour
* Checking version-specific features

Third-party tutorials may be useful, but they can be:

* Outdated
* Incomplete
* Incorrect
* Written for another operating system
* Written for a different software version

Official documentation explains how the tool is intended to work.

---

# Linux Manual Pages

Learned that Linux provides built-in technical documentation called manual pages.

Manual pages are opened using:

```bash
man <command>
```

Examples:

```bash
man nc
man grep
man ssh
man nmap
```

## Common Manual Page Sections

| Section       | Purpose                            |
| ------------- | ---------------------------------- |
| `NAME`        | Command name and short description |
| `SYNOPSIS`    | General command syntax             |
| `DESCRIPTION` | Detailed explanation               |
| `OPTIONS`     | Available command flags            |
| `EXAMPLES`    | Practical command examples         |
| `SEE ALSO`    | Related commands and documentation |

## Manual Page Navigation

| Key     | Action                 |
| ------- | ---------------------- |
| `Space` | Move forward one page  |
| `b`     | Move backward one page |
| `g`     | Go to the beginning    |
| `G`     | Go to the end          |
| `/word` | Search for text        |
| `n`     | Next search result     |
| `N`     | Previous search result |
| `q`     | Quit                   |

---

# Linux Documentation Commands

## `man`

Opens the detailed manual page for a command.

```bash
man nc
```

## `whatis`

Displays a short description of a command.

```bash
whatis nc
```

Example result:

```text
nc (1) - arbitrary TCP and UDP connections and listens
```

## `apropos`

Searches manual-page names and descriptions for a keyword.

```bash
apropos network
```

## `man -k`

Performs a keyword search through manual-page names and descriptions.

```bash
man -k network
```

`apropos network` and `man -k network` generally perform the same type of search.

## `help`

Displays documentation for commands built directly into the shell.

```bash
help cd
```

Learned that `help ls` does not work because `ls` is an external command rather than a Bash built-in.

For `ls`, commands such as the following can be used:

```bash
man ls
whatis ls
info ls
```

---

# New Commands Studied

| Command   | Meaning                         | Purpose                                         | Example                     |
| --------- | ------------------------------- | ----------------------------------------------- | --------------------------- |
| `grep`    | Global Regular Expression Print | Searches text for matching words or patterns    | `grep "error" logfile.txt`  |
| `ssh`     | Secure Shell                    | Securely connects to another computer           | `ssh username@192.168.1.20` |
| `nc`      | Netcat                          | Creates or listens for TCP and UDP connections  | `nc host.example.com 42`    |
| `nmap`    | Network Mapper                  | Scans authorized systems for ports and services | `nmap 192.168.1.20`         |
| `man`     | Manual                          | Opens a Linux command’s manual page             | `man nc`                    |
| `whatis`  | Brief manual description        | Displays a short explanation of a command       | `whatis nc`                 |
| `apropos` | Manual keyword search           | Finds commands related to a search term         | `apropos network`           |
| `man -k`  | Manual keyword search           | Searches manual descriptions by keyword         | `man -k network`            |

---

# Netcat

Learned that `nc` refers to Netcat.

Netcat is a command-line networking utility that can:

* Connect to TCP services
* Connect to UDP services
* Listen for incoming connections
* Send and receive raw text
* Check whether a port is reachable
* Troubleshoot network services

General syntax:

```bash
nc [options] destination port
```

TryHackMe practical example:

```bash
nc host.example.com 42
```

---

# Netcat Options

These are options used with `nc`, not standalone commands.

| Option | Meaning      | Purpose                                | Example                      |
| ------ | ------------ | -------------------------------------- | ---------------------------- |
| `-v`   | Verbose      | Displays additional connection details | `nc -v example.com 80`       |
| `-l`   | Listen       | Waits for an incoming connection       | `nc -l 8080`                 |
| `-n`   | Numeric only | Prevents DNS hostname resolution       | `nc -n 192.168.1.20 80`      |
| `-p`   | Source port  | Selects a local source port            | `nc -p 5000 192.168.1.20 80` |
| `-w`   | Timeout      | Sets the waiting timeout in seconds    | `nc -w 5 192.168.1.20 80`    |

Options can be combined:

```bash
nc -v -n -w 5 192.168.1.20 80
```

---

# Local Linux Practice

Practised documentation and networking commands inside the local Ubuntu terminal.

## Command Description Practice

Used:

```bash
whatis ls
```

Received:

```text
ls (1) - list directory contents
```

Used:

```bash
whatis apropos
```

Received:

```text
apropos (1) - search the manual page names and descriptions
```

Used:

```bash
whatis Netcat
```

Received a description explaining that Netcat supports arbitrary TCP and UDP connections and listening.

## Bash Built-In Help

Attempted:

```bash
help ls
```

Received an error because `ls` is not a Bash built-in command.

Used:

```bash
help cd
```

Successfully opened Bash’s built-in documentation for changing the current working directory.

This demonstrated the difference between:

* Bash built-in commands
* External Linux programs

---

# Netcat Connection Practice

Used Netcat against my own domain:

```bash
nc jast.mortgage 42
```

Observed that the normal Bash prompt disappeared while Netcat controlled the terminal.

Text entered during the active session was passed to the Netcat connection rather than interpreted as Linux commands.

After the connection ended, the Bash prompt returned.

Learned:

```text
Prompt visible   = Bash is waiting for a command
Prompt missing   = Another program currently controls the terminal
```

Used the following connection test:

```bash
nc -v -w 5 jast.mortgage 443
```

Received:

```text
Connection to jast.mortgage (67.205.6.229) 443 port [tcp/https] succeeded!
```

This confirmed that:

* The domain resolved to an IP address
* Port 443 was reachable
* A TCP connection was successfully established
* Port 443 was accepting connections

It did not prove that:

* The website was completely healthy
* The HTTPS certificate was valid
* The server was secure
* The web application was functioning correctly

It only confirmed that the TCP port was reachable.

---

# Nmap Practice

Attempted:

```bash
nmap 67.205.6.229
```

The terminal reported:

```text
Command 'nmap' not found
```

Learned that Nmap was not installed on the local Ubuntu system.

Ubuntu suggested installation through either `snap` or `apt`.

The standard Ubuntu package-manager method is:

```bash
sudo apt update
sudo apt install nmap
```

Nmap installation can be verified using:

```bash
nmap --version
```

Nmap should only be used against:

* Systems I own
* Approved lab systems
* TryHackMe targets
* Systems I have explicit permission to scan

---

# GitHub for Vulnerability Research

Learned that GitHub is commonly used by security researchers to publish:

* Proof-of-concept code
* Exploitation tools
* Vulnerability scanners
* Detection scripts
* Technical analyses
* Patch comparisons
* Indicators of compromise
* Research reports

Searching for a CVE identifier may reveal related repositories.

Example:

```text
CVE-2026-1337
```

However, GitHub does not guarantee that uploaded code is:

* Safe
* Accurate
* Complete
* Functional
* Non-malicious

---

# Evaluating GitHub Security Repositories

Before executing code from a repository, check:

* The author’s account and history
* The repository creation date
* Previous contributions
* The README documentation
* Commit history
* Issues and pull requests
* Source code
* Dependencies
* Installation scripts
* Connections to external domains or IP addresses
* Whether trusted researchers reference the project

A large number of stars does not prove that a project is safe.

## Important Repository Terms

| Term         | Meaning                               |
| ------------ | ------------------------------------- |
| Repository   | Project files and version history     |
| Clone        | Download a repository and its history |
| Fork         | Create a personal GitHub copy         |
| Commit       | A saved change                        |
| Branch       | A separate development line           |
| Pull request | A proposed change                     |
| Issue        | A reported problem or discussion      |
| Release      | A packaged project version            |
| Star         | Bookmark or expression of interest    |

## Useful GitHub and Code-Review Commands

```bash
git clone <repository-address>
```

Downloads a repository and its Git history.

```bash
cd <repository>
```

Moves into the repository directory.

```bash
ls -la
```

Lists all repository files, including hidden files.

```bash
less README.md
```

Reads the project documentation.

```bash
less script.py
```

Reviews a script without executing it.

```bash
grep -n "word" script.py
```

Searches a script and displays matching line numbers.

---

# Safe Proof-of-Concept Workflow

Before testing a PoC:

1. Confirm the CVE through an official vulnerability source.
2. Read the affected vendor’s advisory.
3. Confirm the affected product and version.
4. Check the repository author and history.
5. Read the README.
6. Inspect the source code.
7. Review dependency and installation files.
8. Compare the PoC with independent research.
9. Use a disposable or isolated lab.
10. Test only systems with explicit authorization.
11. Avoid using `sudo` unless it is understood and necessary.
12. Restore the test environment afterward.

Unknown PoC code should never be executed on a main computer containing:

* Personal files
* Browser sessions
* Saved passwords
* SSH keys
* Work information
* Client information

---

# Search Skills Workflow

```text
Identify the product, service, file, URL, or vulnerability
                         ↓
Use the appropriate specialized search resource
                         ↓
Read official documentation and vendor advisories
                         ↓
Compare findings across multiple trusted sources
                         ↓
Evaluate severity, exposure, and organizational risk
                         ↓
Review PoC or scanner code before execution
                         ↓
Test only inside an isolated and authorized environment
```

---

# Resource Comparison

| Resource               | Main Purpose                                    |
| ---------------------- | ----------------------------------------------- |
| Shodan                 | Searches publicly exposed systems and services  |
| VirusTotal             | Checks files, URLs, domains, IPs, and hashes    |
| CVE databases          | Catalogues known vulnerabilities                |
| CVSS                   | Measures technical vulnerability severity       |
| Exploit-DB             | Archives exploits and Proof-of-Concept material |
| Official documentation | Explains correct product and tool usage         |
| Linux `man` pages      | Provides local command documentation            |
| GitHub                 | Hosts source code, research, scanners, and PoCs |

---

# Key Lessons

* Search skills are a major part of cybersecurity work.
* Specialized services provide different types of information.
* Search results should always be verified.
* A service banner does not prove that a system is vulnerable.
* VirusTotal detections provide evidence, not certainty.
* Zero antivirus detections does not prove that something is safe.
* CVE identifies a vulnerability.
* CVSS measures its technical severity.
* Severity and organizational risk are not the same thing.
* Official documentation should be checked before relying on tutorials.
* `man`, `whatis`, `apropos`, and `help` provide different forms of Linux documentation.
* Netcat can test TCP and UDP connections.
* An open port proves reachability, not complete security or functionality.
* GitHub repositories and PoCs must be inspected before execution.
* Publicly available exploit code is not permission to test public systems.
* All scans and vulnerability tests must remain within authorized scope.

---

# Room Completion

Completed all six tasks in the TryHackMe **Search Skills** room:

* Introduction
* Shodan
* VirusTotal
* Vulnerability databases and CVEs
* Technical documentation and Linux manual pages
* GitHub vulnerability research

This was the first completed room in the **Cyber Security 101** learning path.
