# Day 31 – Windows Fundamentals 3

## TryHackMe Room

Windows Fundamentals 3

---

# Topics Covered

Today I started the Windows Fundamentals 3 room on TryHackMe and focused on selected important tasks related to built-in Windows security and recovery features.

The main areas covered were:

* Windows Updates
* Windows Security
* Virus & Threat Protection
* Firewall & Network Protection
* App & Browser Control
* Device Security
* BitLocker
* Volume Shadow Copy Service
* Practical Windows firewall and printer troubleshooting
* PowerShell alternate data streams command practice

---

# Windows Updates

Windows Update is a Microsoft service used to provide:

* security updates
* operating system patches
* feature improvements
* Microsoft Defender updates
* updates for other Microsoft products

Updates are commonly released on the second Tuesday of each month, known as **Patch Tuesday**.

Critical security updates do not always wait for Patch Tuesday. If a vulnerability is urgent, Microsoft can release an update immediately through Windows Update.

## Useful Command

Windows Update can be opened from Run or Command Prompt with:

```cmd
control /name Microsoft.WindowsUpdate
```

## Key Takeaways

* Windows updates help keep the operating system secure and stable.
* Updates may require a restart.
* Home users usually control their own update settings.
* Lab, work, or school machines may show update settings as managed by an organization.
* Updates should not be ignored because many security fixes are delivered through Windows Update.

---

# Windows Security

Windows Security is the central dashboard for managing built-in Windows protection features.

Main protection areas include:

* Virus & threat protection
* Firewall & network protection
* App & browser control
* Device security

## Windows Security Status Icons

| Icon Color | Meaning                                    |
| ---------- | ------------------------------------------ |
| Green      | Device is sufficiently protected           |
| Yellow     | There is a safety recommendation to review |
| Red        | Immediate attention is needed              |

## Key Takeaway

Windows Security gives a quick overview of the device's protection status and provides access to important built-in security tools.

---

# Virus & Threat Protection

Virus & threat protection is used to manage Microsoft Defender Antivirus features.

It includes:

* current threats
* scan options
* threat history
* real-time protection
* cloud-delivered protection
* automatic sample submission
* controlled folder access
* exclusions
* protection updates
* ransomware protection

---

## Scan Options

| Scan Type   | Description                                                 |
| ----------- | ----------------------------------------------------------- |
| Quick scan  | Checks common locations where threats are usually found     |
| Full scan   | Checks all files and running programs on the hard disk      |
| Custom scan | Allows the user to choose specific files or folders to scan |

---

## Threat History

| Item                | Meaning                                               |
| ------------------- | ----------------------------------------------------- |
| Last scan           | Shows the most recent scan activity                   |
| Quarantined threats | Threats that were isolated and prevented from running |
| Allowed threats     | Detected threats that the user allowed to run         |

Allowing detected threats is risky and should only be done when the user is completely sure the item is safe.

---

## Virus & Threat Protection Settings

| Setting                     | Purpose                                                    |
| --------------------------- | ---------------------------------------------------------- |
| Real-time protection        | Locates and stops malware from installing or running       |
| Cloud-delivered protection  | Uses cloud-based threat intelligence for faster protection |
| Automatic sample submission | Sends suspicious samples to Microsoft for analysis         |
| Controlled folder access    | Helps protect files and folders from unauthorized changes  |
| Exclusions                  | Allows files or folders to be ignored by antivirus scans   |
| Notifications               | Sends security and health alerts                           |

## Important Warning

Exclusions can create security risk because excluded files and folders are ignored by Microsoft Defender. They should only be used when necessary and when the user understands the risk.

## Practical Tip

A file or folder can be scanned manually by right-clicking it and selecting:

```text
Scan with Microsoft Defender
```

---

# Firewall & Network Protection

A firewall controls network traffic going into and out of a device.

It helps decide what is allowed or blocked through network ports.

## Windows Firewall Profiles

| Profile | Description                                                                          |
| ------- | ------------------------------------------------------------------------------------ |
| Domain  | Used on networks where the device can authenticate to a domain controller            |
| Private | Used for trusted home or private networks                                            |
| Public  | Used for untrusted networks such as coffee shops, airports, hotels, and public Wi-Fi |

## Simple Profile Breakdown

| Network Type | Best Use                            |
| ------------ | ----------------------------------- |
| Domain       | Company or school managed network   |
| Private      | Home or trusted network             |
| Public       | Unknown or untrusted public network |

For a home Wi-Fi network, the profile should usually be set to **Private**.

For coffee shops, airports, hotels, or unknown networks, the profile should usually be **Public**.

---

## Allow an App Through Firewall

Windows allows users to control which apps can communicate through the firewall.

An app can be allowed on:

* Private networks
* Public networks
* both network types

Apps should only be allowed on Public networks if there is a real need.

For home use, printer and scanner apps should usually be allowed on **Private**, not Public.

---

## Useful Firewall Command

The advanced Windows Defender Firewall console can be opened with:

```cmd
WF.msc
```

---

# Practical Firewall and Printer Troubleshooting

I also explored Windows firewall and printer settings on my own laptop while troubleshooting a Brother DCP-L2640DW printer/scanner connection issue.

## What I Checked

* Windows Defender Firewall allowed apps
* Brother Network Scanner firewall permissions
* Brother Print Support App firewall permissions
* Brother iPrint&Scan firewall permissions
* Private vs Public firewall profile settings
* Windows printer default settings
* Printer ports
* USB port vs TCP/IP network port

## Important Discovery

The Brother printer entry was using a network port:

```text
Standard TCP/IP Port
```

This means the selected printer entry was configured as a network printer, not only as a USB printer.

A USB printer port would usually appear as something like:

```text
USB001
```

A network printer port may appear as:

```text
Standard TCP/IP Port
WSD
Brother TCP/IP Port
192.168.x.x
```

## Practical Takeaway

When a wireless printer does not work properly, it is important to check whether Windows is using:

* the USB printer entry
* the network printer entry
* the correct TCP/IP or WSD port
* the correct default printer

I also learned that **Let Windows manage my default printer** can sometimes cause confusion because Windows may automatically choose the last-used printer instead of the one I actually want as default.

---

# App & Browser Control

App & browser control includes Microsoft Defender SmartScreen and exploit protection.

## Microsoft Defender SmartScreen

SmartScreen helps protect against:

* phishing websites
* malicious websites
* suspicious downloads
* unrecognized apps
* potentially malicious files from the web

SmartScreen can usually be set to:

| Setting | Meaning                                    |
| ------- | ------------------------------------------ |
| Block   | Stops suspicious content more aggressively |
| Warn    | Warns the user before continuing           |
| Off     | Disables the protection                    |

Turning SmartScreen off is not recommended for normal use.

---

## Exploit Protection

Exploit protection is built into Windows and helps protect applications and system processes from certain attack techniques.

An exploit is an attack that takes advantage of a weakness in software.

Exploit protection is an advanced area, and the default settings should usually be left unchanged unless the user knows exactly what they are doing.

---

# Device Security

Device security covers hardware-backed Windows protection features.

Important features include:

* Core isolation
* Memory integrity
* Security processor
* TPM

---

## Core Isolation

Core isolation helps separate important Windows processes from the rest of the system.

This adds an extra layer of protection around sensitive parts of Windows.

---

## Memory Integrity

Memory Integrity helps prevent attacks from inserting malicious code into high-security processes.

This is useful because some attacks attempt to abuse memory and running processes instead of simply running as normal files.

---

## Trusted Platform Module

TPM stands for:

```text
Trusted Platform Module
```

A TPM is a hardware or firmware-based security component that helps with cryptographic operations.

In simple terms, TPM acts like a secure vault inside the computer that helps protect sensitive security information.

TPM is commonly used with:

* BitLocker
* encryption keys
* device integrity checks
* credential protection
* tamper detection

---

# BitLocker

BitLocker is a Windows drive encryption feature.

It helps protect data if a device is:

* lost
* stolen
* accessed offline
* improperly disposed of
* removed from the original computer

## BitLocker and TPM

BitLocker provides stronger protection when used with TPM.

The TPM helps protect the encryption keys and helps verify that the computer has not been tampered with while offline.

## Important Reminder

The BitLocker recovery key must be saved somewhere safe.

If the recovery key is lost, the user may lose access to the encrypted data.

---

# Volume Shadow Copy Service

Volume Shadow Copy Service, also known as **VSS**, helps create snapshots of files or system data.

A shadow copy is a point-in-time copy that can be used for recovery.

VSS supports features such as:

* restore points
* system restore
* backup consistency
* previous versions of files

Shadow copies are stored in the **System Volume Information** folder on drives where protection is enabled.

---

## Security Concern

VSS is useful, but it is not a complete backup strategy.

Ransomware may try to delete shadow copies so the victim cannot easily restore files after encryption.

This is why proper backups should include:

* offline backups
* off-site backups
* cloud backups with version history

## Key Takeaway

VSS can help with recovery, but it should not be trusted as the only recovery option.

---

# PowerShell Practice

I also practiced a PowerShell command related to alternate data streams.

## Alternate Data Streams Command

To view alternate data streams for a file:

```powershell
Get-Item C:\temp\file.txt -Stream *
```

## Meaning

| Part             | Meaning                                        |
| ---------------- | ---------------------------------------------- |
| Get-Item         | Gets information about a file or item          |
| C:\temp\file.txt | Target file                                    |
| -Stream *        | Shows all alternate data streams for that file |

---

# Commands Learned

| Command                                 | Purpose                                                |
| --------------------------------------- | ------------------------------------------------------ |
| `control /name Microsoft.WindowsUpdate` | Opens Windows Update                                   |
| `WF.msc`                                | Opens Windows Defender Firewall with Advanced Security |
| `Get-Item C:\temp\file.txt -Stream *`   | Views alternate data streams for a file                |

---

# Key Cybersecurity Takeaways

* Windows Update is important because many security patches are delivered through it.
* Windows Security is the main dashboard for built-in Windows protection.
* Microsoft Defender can scan files, quarantine threats, and provide real-time protection.
* Firewall profiles matter because Private and Public networks should not be treated the same.
* SmartScreen helps protect against phishing, malware websites, suspicious downloads, and unknown apps.
* Exploit protection helps harden Windows against attack techniques.
* TPM provides hardware-backed security functions.
* BitLocker protects data through drive encryption.
* VSS can help with recovery, but ransomware may attempt to delete shadow copies.
* Offline and off-site backups are still important.
* Practical clicking through Windows settings helps build a real mental map of Windows security.

---

# Personal Notes

This room was useful because it connected Windows security theory to real settings inside the operating system.

I found the practical exploration valuable because I could see where these protections live in Windows, what they look like, and how they relate to real troubleshooting.

Rather than only memorizing definitions, I explored the settings directly and connected them to practical cybersecurity concepts such as endpoint protection, hardening, encryption, firewall rules, ransomware recovery, and system updates.
