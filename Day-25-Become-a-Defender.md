# Day 25 – Become a Defender

## TryHackMe Room

**Become a Defender**

This room introduced the foundations of defensive security, including understanding an organization's infrastructure, gaining visibility into systems, anticipating attack paths, and applying layered security controls.

This room also marked the completion of the **TryHackMe Pre Security learning path**.

---

# Learning Objectives

* Understand what defensive security means
* Learn what defenders are responsible for protecting
* Understand why visibility is essential
* Identify common parts of a client environment
* Recognize suspicious behaviour
* Learn the difference between prevention, detection, mitigation, analysis, and response
* Understand how attackers move between connected systems
* Match common security controls to different systems
* Develop a defender mindset
* Understand how defensive knowledge supports penetration testing and red teaming

---

# What Is Defensive Security?

Defensive security focuses on protecting systems, networks, users, applications, and data from cyberattacks.

Defenders work to:

* Prevent attacks
* Detect suspicious activity
* Limit damage
* Investigate incidents
* Recover affected systems
* Improve security controls

Defensive security professionals are often known as the **Blue Team**.

A simple comparison is:

```text
Red Team:
How can this system be compromised?

Blue Team:
How can we prevent, detect, contain, and respond to that compromise?
```

Defenders must understand how attackers think because attackers often use predictable techniques and attack paths.

---

# The CIA Triad

Defensive security supports the three goals of the CIA triad.

## Confidentiality

Ensures that information is only accessible to authorized users.

Examples:

* Access controls
* Passwords
* Encryption
* Multi-factor authentication

## Integrity

Ensures that information and systems are not changed improperly.

Examples:

* File integrity monitoring
* Permissions
* Logging
* Digital signatures

## Availability

Ensures that systems and information remain accessible when needed.

Examples:

* Backups
* Redundant systems
* Software maintenance
* Denial-of-service protection

---

# Understanding the Environment

Before defenders can protect an organization, they must understand what exists inside the environment.

This includes:

* Employee devices
* Servers
* Applications
* Databases
* Networks
* Firewalls
* User accounts
* Cloud services
* Sensitive information

A defender should understand:

* What each asset does
* Who uses it
* Where it is located
* What information it contains
* How it communicates with other systems
* Whether it is exposed to the internet
* What could happen if it were compromised

You cannot properly protect something if you do not know it exists.

---

# Client Infrastructure

**Client infrastructure** refers to the systems and technology belonging to the organization being protected.

Examples include:

* Workstations
* Laptops
* Servers
* Networks
* Firewalls
* Websites
* Applications
* Databases
* Email systems
* Cloud services

In this context, the word **client** means the organization receiving cybersecurity services.

This is different from a **client device** in the client-server model.

---

# Assets

An **asset** is anything valuable that an organization needs to protect.

Examples:

* Employee laptop
* Administrator account
* Customer database
* Web server
* Email server
* Business application
* Sensitive document
* Network equipment

Some assets are more important than others.

Systems containing sensitive information or supporting essential business operations are often called **high-value assets**.

The most important systems and information may informally be called the organization's **crown jewels**.

---

# Endpoints

An **endpoint** is a device connected to a network that communicates with other systems.

Examples:

* Laptop
* Desktop computer
* Smartphone
* Tablet
* Server
* Network-connected printer

An endpoint is the **device**, not the employee.

Example:

```text
Employee = User
Laptop = Endpoint
Laptop requesting services = Client device
Server providing services = Server
```

An employee laptop can be both an endpoint and a client device.

---

# Visibility

**Visibility** means being able to observe activity across an organization's systems and networks.

Sources of visibility include:

* Login logs
* Firewall logs
* Web server logs
* Network traffic
* Antivirus alerts
* Endpoint activity
* Email security alerts
* Cloud activity records

Visibility helps defenders answer questions such as:

* Who signed in?
* Which device was used?
* Where did the connection originate?
* What files were accessed?
* What programs were executed?
* Was information modified?
* Did unusual network traffic occur?

Without visibility, attacks may go unnoticed and investigations become much more difficult.

---

# Normal and Suspicious Behaviour

Defenders need to understand what normal activity looks like before they can recognize unusual behaviour.

Examples of suspicious behaviour include:

* Repeated failed login attempts
* Logins from unusual IP addresses
* Access at unexpected times
* Large amounts of information leaving the network
* Unexpected software execution
* Changes to important files
* Access to systems the user does not normally use
* Connections to known malicious servers

Suspicious activity is not always proof of an attack.

For example, an unusual login may be caused by:

* An employee travelling
* Remote work
* A VPN
* A legitimate late-night shift
* An attacker using stolen credentials

Security alerts must be analyzed in context.

---

# Scope

**Scope** defines which systems, networks, accounts, and information the security team is authorized and responsible to protect.

Defenders do not protect everything on the internet.

A typical scope might include:

* Company laptops
* Employee accounts
* Internal networks
* Websites
* Servers
* Databases
* Email systems
* Cloud services

Examples outside the scope may include:

* Another company's server
* Random websites
* Unrelated personal accounts
* Systems without authorization

Scope is important for legal, ethical, and operational reasons.

---

# City Analogy

TryHackMe compared an organization's infrastructure to a city.

```text
City Component             Security Equivalent

Homes                      Employee devices
People                     Users
Shops and public buildings Web servers
Post office                Mail server
City gate                  Firewall
Roads                      Network connections
Cameras and patrols        Logs and monitoring
Locked-door attempts       Failed login attempts
Police response            Incident response
Blocked roads              Firewall or IP blocking
Outside the city           Internet
```

Like city guards, defenders must know:

* What exists inside the environment
* Where important assets are located
* What normal activity looks like
* What behaviour may be suspicious
* How to respond when trouble occurs

---

# Foundational Defensive Security Functions

## Prevention

Prevention means stopping or reducing opportunities for attacks before they succeed.

Examples:

* Firewalls
* Antivirus
* Multi-factor authentication
* Strong passwords
* Software patching
* Access controls
* Email filtering
* Employee security training

Prevention asks:

```text
How can we stop this from happening?
```

---

## Detection

Detection means identifying suspicious or malicious activity.

Examples:

* Monitoring logs
* Generating security alerts
* Detecting malware
* Identifying unusual login activity
* Monitoring network traffic
* Detecting unauthorized file changes

Detection asks:

```text
How will we know something suspicious is happening?
```

---

## Mitigation

Mitigation means taking immediate action to reduce the impact of an incident.

Examples:

* Isolating an infected computer
* Blocking an IP address
* Disabling a compromised account
* Stopping malicious traffic
* Temporarily disabling a vulnerable service

Mitigation asks:

```text
How can we stop the situation from getting worse?
```

---

## Analysis

Analysis means investigating the incident to determine:

* What happened
* How it happened
* When it started
* Which accounts were involved
* Which systems were affected
* Whether the attacker still has access
* Whether information was accessed or stolen

Evidence may include:

* Logs
* Security alerts
* Network traffic
* Emails
* Running processes
* File changes
* Account activity

Analysis asks:

```text
What happened, how did it happen, and what was affected?
```

---

## Response and Improvement

Response involves removing the threat and restoring normal operations.

Examples:

* Removing malware
* Resetting passwords
* Restoring systems from backups
* Closing unauthorized access
* Rebuilding compromised systems

Improvement involves strengthening security after the incident.

Examples:

* Installing missing patches
* Updating firewall rules
* Improving monitoring
* Adding MFA
* Updating incident-response procedures
* Providing security training

Defensive security is a continuous cycle:

```text
Understand the environment
        ↓
Prevent attacks
        ↓
Detect suspicious activity
        ↓
Mitigate the threat
        ↓
Analyze the incident
        ↓
Respond and recover
        ↓
Improve defenses
        ↓
Continue monitoring
```

---

# The Defender Mindset

A defender must look beyond individual devices and see the environment as an interconnected system.

Attackers rarely compromise only one asset.

They may compromise an initial device and then use it to reach more valuable systems.

Example attack path:

```text
Malicious email
       ↓
Employee opens attachment
       ↓
Workstation is compromised
       ↓
Credentials are stolen
       ↓
Attacker accesses internal services
       ↓
Attacker reaches database
       ↓
Sensitive information is stolen
```

Each stage gives defenders another opportunity to prevent, detect, or stop the attack.

---

# Initial Access

**Initial access** is the attacker's first successful entry into an environment.

Possible initial-access methods include:

* Phishing emails
* Malicious attachments
* Stolen passwords
* Vulnerable public servers
* Unsafe downloads
* Misconfigured remote-access services

Initial access does not always give the attacker immediate access to the final target.

It may only provide the first stepping stone.

---

# Pivoting and Lateral Movement

## Pivoting

**Pivoting** means using one compromised system to reach another part of the environment.

Example:

```text
Internet
   ↓
Employee workstation
   ↓
Internal server
   ↓
Database
```

## Lateral Movement

**Lateral movement** means moving between systems inside an environment after initial access has been obtained.

Example:

```text
Compromised workstation
        ↓
File server
        ↓
Administrator account
        ↓
Database server
```

Defenders monitor for lateral movement because it may show that an attacker is expanding their access.

---

# Key Defender Principles

## Threat Anticipation

Threat anticipation means asking realistic “What if?” questions.

Examples:

* What if an employee opens a malicious attachment?
* What if a password is stolen?
* What if the web server is not patched?
* What if one workstation is compromised?
* What if malware attempts to spread?
* What if an attacker reaches the customer database?

The goal is to anticipate realistic attack paths and prepare controls before an attack occurs.

---

## Attack Awareness

Attacks often follow recognizable stages.

A simplified attack chain might include:

```text
Reconnaissance
      ↓
Initial access
      ↓
Execution
      ↓
Credential theft
      ↓
Privilege escalation
      ↓
Lateral movement
      ↓
Sensitive system access
      ↓
Data theft or disruption
```

Understanding attack chains helps defenders identify where controls should be placed.

---

## Risk Prioritization

Not every system carries the same level of risk.

Defenders prioritize assets based on:

* The sensitivity of the information
* The importance of the service
* Exposure to the internet
* The likelihood of attack
* The possible damage
* Dependencies from other systems

A customer database requires stronger protection than an unused test computer because the potential impact is much greater.

---

## Continuous Adaptation

Security is not a one-time setup.

Defenders must continuously adapt because:

* New vulnerabilities are discovered
* Attack techniques change
* Employees join or leave
* New devices are added
* Software changes
* Cloud services are introduced
* Business requirements evolve

Defenders regularly:

* Install patches
* Review firewall rules
* Update security tools
* Remove unused accounts
* Improve monitoring
* Study new threats
* Review previous incidents

---

# Threat, Vulnerability, and Risk

## Threat

A **threat** is something capable of causing harm.

Examples:

* Attacker
* Malware
* Malicious employee
* Ransomware group
* Automated malicious bot

## Vulnerability

A **vulnerability** is a weakness that could be exploited.

Examples:

* Weak password
* Outdated software
* Incorrect permissions
* Exposed service
* Poor configuration

## Risk

**Risk** is the likelihood and potential impact of a threat successfully exploiting a vulnerability.

A simplified relationship is:

```text
Threat + Vulnerability + Potential Impact = Risk
```

Another simplified model is:

```text
Risk = Likelihood × Impact
```

Example:

```text
Threat:
Attacker

Vulnerability:
Unpatched web server

Potential impact:
Customer information is stolen

Risk:
Data breach
```

---

# Defence in Depth

No single security control can stop every attack.

**Defence in depth** means using several overlapping security layers.

Physical example:

```text
Fence
  +
Locked door
  +
Security guard
  +
Alarm
  +
Camera
```

Cybersecurity example:

```text
Firewall
  +
Email filtering
  +
Antivirus
  +
Software patching
  +
MFA
  +
Monitoring
  +
Backups
```

If one control fails, another may still prevent, detect, or limit the attack.

Example:

```text
Spam filter misses phishing email
              ↓
Employee opens attachment
              ↓
Endpoint protection detects malware
              ↓
Device is isolated
              ↓
Security team investigates
```

---

# Attack Surface

The **attack surface** is the collection of possible points that an attacker could target.

Examples:

* Open ports
* Public login pages
* User accounts
* Internet-facing services
* Web applications
* Outdated software
* Exposed remote-access services

Reducing the attack surface means:

* Closing unnecessary ports
* Disabling unused accounts
* Removing unused software
* Restricting access
* Exposing only necessary services

---

# Protecting Employee Devices

Employee devices are commonly called endpoints.

## Possible risks

* Malicious links
* Unsafe downloads
* Malicious attachments
* Malware
* Stolen passwords
* Outdated software
* Lost or stolen devices

## Security controls

* Antivirus
* Endpoint protection
* Software updates
* Patching
* Multi-factor authentication
* Device encryption
* Access controls
* Application restrictions
* Security-awareness training
* Backups

---

# Antivirus and Endpoint Protection

## Antivirus

Antivirus primarily looks for malicious programs and files.

It may:

* Scan files
* Detect known malware
* Quarantine suspicious files
* Block harmful programs
* Generate alerts

## Endpoint Protection

Modern endpoint protection can monitor more than files.

It may examine:

* Running processes
* File changes
* Network connections
* Login activity
* Suspicious commands
* Behaviour associated with attacks

---

# Patching

A **patch** is a software update that fixes a problem or vulnerability.

Regular patching reduces the opportunity for attackers to exploit known weaknesses.

An unpatched system may remain vulnerable even when a fix is already available.

---

# Protecting a Web Server

A web server may host:

* Public websites
* Web applications
* Customer portals
* Online business services

## Possible risks

* Vulnerability exploitation
* Unauthorized access
* Malicious web requests
* Password attacks
* Data interception
* Denial-of-service attacks

## Security controls

* Allow only necessary traffic
* Use HTTPS
* Install patches
* Apply strong authentication
* Restrict administrative access
* Use secure configurations
* Monitor web activity
* Perform vulnerability testing

---

# HTTPS

HTTPS encrypts communication between a browser and a web server.

It helps protect information from being:

* Read while travelling across the network
* Modified during transmission

HTTPS does not automatically make a website completely secure.

A vulnerable application can still be attacked through an encrypted HTTPS connection.

---

# Protecting a Mail Server

A mail server sends and receives organizational email.

## Possible risks

* Phishing
* Malicious attachments
* Spam
* Email spoofing
* Compromised email accounts
* Business email compromise

## Security controls

* Spam filters
* Attachment scanning
* Link scanning
* Sender verification
* Multi-factor authentication
* Email account monitoring
* Employee phishing training
* Blocking dangerous attachment types

---

# Protecting Networks with Firewalls

A firewall controls network traffic using security rules.

Firewall rules may consider:

* Source IP address
* Destination IP address
* Port
* Protocol
* Whether traffic should be allowed or blocked

Example:

```text
Allow:
Internet users to access the public web server on port 443

Block:
Internet users from directly accessing the internal database
```

---

# Default Deny

A **default-deny** approach blocks access or traffic unless it is specifically allowed.

Example:

```text
Block everything by default
        ↓
Allow only the services required for business
```

This is safer than allowing everything and attempting to block individual threats afterward.

---

# IP Address Blocking

Known malicious IP addresses may be blocked.

However, IP blocking is not perfect because attackers may:

* Change IP addresses
* Use VPNs
* Use proxies
* Use cloud servers
* Use compromised computers

IP blocking should be one layer of defence rather than the only control.

---

# Inbound and Outbound Traffic

## Inbound Traffic

Traffic entering the organization's environment.

Examples:

* Website visitors
* Incoming emails
* Remote login attempts
* Connections from external systems

Defenders restrict inbound traffic to only what is required.

## Outbound Traffic

Traffic leaving the organization's environment.

Outbound traffic may reveal:

* Malware contacting an attacker
* Stolen information leaving the network
* Unauthorized cloud uploads
* A compromised computer contacting a command-and-control server

Defenders should monitor both inbound and outbound activity.

---

# Matching Risks to Security Controls

```text
Asset or Risk                  Security Control

Malicious email                Spam filter
Malicious attachment           Attachment scanning
Malware on workstation         Antivirus or endpoint protection
Stolen password                Multi-factor authentication
Unpatched web server           Software patching
Intercepted web traffic        HTTPS
Unauthorized network traffic   Firewall
Compromised device             Network isolation
Unauthorized database access   Access controls
Data loss or ransomware        Backups
Unusual login activity         Logging and monitoring
```

Good defenders match controls to specific risks rather than installing tools without understanding their purpose.

---

# Example of Layered Defences

Example attack:

```text
1. Attacker sends malicious attachment
2. Employee opens the attachment
3. Malware infects workstation
4. Attacker steals credentials
5. Attacker accesses internal services
6. Attacker reaches database
7. Sensitive information is stolen
```

Possible defensive controls:

```text
Stage 1:
Spam filter blocks the email

Stage 2:
Attachment scanner identifies the file

Stage 3:
Endpoint protection blocks the malware

Stage 4:
MFA prevents use of the stolen password

Stage 5:
Login monitoring detects unusual access

Stage 6:
Network segmentation blocks database access

Stage 7:
Outbound monitoring detects data leaving the network
```

Every attack stage creates another opportunity to stop or detect the attacker.

---

# Defensive Security Career Areas

## Security Operations Centre

A **Security Operations Centre (SOC)** monitors systems and networks for suspicious activity.

SOC analysts may:

* Review security alerts
* Examine logs
* Investigate unusual activity
* Check IP addresses and files
* Determine the seriousness of alerts
* Escalate incidents
* Document findings

### Triage

**Triage** is the initial review of an alert to determine:

* What caused it
* Whether it may be a false positive
* How serious it is
* Which systems or users are affected
* Whether escalation is required

---

## Threat Intelligence

Threat intelligence professionals research:

* Attackers
* Threat groups
* Malware campaigns
* Phishing infrastructure
* Vulnerabilities
* Malicious IP addresses and domains
* Attacker techniques
* Cyberattack trends

Their research helps organizations prepare for likely threats.

---

## Digital Forensics and Incident Response

This field is commonly called **DFIR**.

### Digital Forensics

Digital forensics involves collecting and examining digital evidence.

Possible evidence includes:

* Files
* Hard drives
* Memory
* Logs
* Emails
* Browser history
* Network activity
* Malware traces

### Incident Response

Incident response involves:

* Confirming an incident
* Containing the threat
* Investigating the attack
* Removing malicious access
* Recovering systems
* Documenting findings
* Improving defenses

A simplified incident-response process is:

```text
Preparation
     ↓
Detection and analysis
     ↓
Containment
     ↓
Threat removal
     ↓
Recovery
     ↓
Lessons learned
```

---

# Extended Learning

## Prevention vs Detection

```text
Prevention:
Attempts to stop an attack

Detection:
Identifies that an attack or suspicious action occurred
```

Example:

```text
Firewall blocks connection = Prevention
Firewall generates alert    = Detection
```

---

## Detection vs Analysis

```text
Detection:
Finds something suspicious

Analysis:
Determines what the activity means
```

Example:

```text
100 failed logins detected     = Detection
Determining whether it was an attacker = Analysis
```

---

## Mitigation vs Response

```text
Mitigation:
Immediately limits damage

Response:
Handles the wider incident and recovery
```

Example:

```text
Disconnect infected laptop = Mitigation
Remove malware and restore laptop = Response
```

---

## Threat vs Vulnerability

```text
Threat:
Something capable of causing harm

Vulnerability:
A weakness that could be exploited
```

Example:

```text
Attacker         = Threat
Unpatched server = Vulnerability
```

---

## Vulnerability vs Risk

```text
Vulnerability:
The weakness itself

Risk:
The potential harm if the weakness is exploited
```

Example:

```text
Weak password                  = Vulnerability
Account takeover and data loss = Risk
```

---

## Antivirus vs Firewall

```text
Antivirus:
Protects a device by detecting malicious files,
programs, and behaviour

Firewall:
Controls network traffic entering or leaving systems
```

They protect different areas and are commonly used together.

---

# How Defensive Knowledge Supports Penetration Testing

My main career direction is **penetration testing**, with the long-term goal of becoming a **red teamer**.

Defensive security is still important because a penetration tester or red teamer should understand:

* How defenders monitor systems
* Which actions create logs
* How attacks may be detected
* How endpoint protection works
* How firewalls restrict traffic
* How SOC analysts investigate alerts
* How organizations prioritize risk
* How findings should be explained to clients
* How recommended controls reduce real business risk

Understanding both attack and defence makes offensive testing more realistic and useful.

The objective of ethical hacking is not only to gain access. It is to identify weaknesses, demonstrate their impact safely, and help the organization improve its security.

---

# Current Offensive-Security Learning Direction

```text
Pre Security – Completed
          ↓
Cyber Security 101
          ↓
Jr Penetration Tester
          ↓
PortSwigger Web Security Academy
          ↓
Hack The Box beginner labs
          ↓
eJPT preparation and certification
          ↓
Build practical portfolio and lab write-ups
          ↓
Apply for junior penetration-testing or related roles
          ↓
Continue toward PNPT and advanced practical training
          ↓
OSCP later
          ↓
Red Team specialization
```

SOC learning may still be used as supporting defensive knowledge, but it is not the main career path.

---

# Key Terminology Cheat Sheet

```text
BLUE TEAM
Cybersecurity professionals who protect systems,
monitor activity, investigate threats, and respond
to incidents.

CLIENT INFRASTRUCTURE
The devices, servers, networks, applications, accounts,
and information belonging to the organization being protected.

ASSET
Anything valuable that an organization needs to protect.

ENDPOINT
A device connected to a network that communicates with
other systems.

VISIBILITY
The ability to observe activity through logs, alerts,
traffic, and monitoring tools.

SCOPE
The systems and information that defenders are authorized
and responsible to protect.

THREAT
Something capable of causing harm.

VULNERABILITY
A weakness that could be exploited.

RISK
The likelihood and potential impact of a threat
successfully causing harm.

PREVENTION
Stopping or reducing the opportunity for attacks.

DETECTION
Identifying suspicious or malicious activity.

MITIGATION
Taking immediate action to limit damage.

ANALYSIS
Investigating what happened, how it happened,
and which systems were affected.

RESPONSE
Removing the threat, recovering systems,
and restoring normal operations.

INITIAL ACCESS
The attacker's first successful entry into an environment.

PIVOTING
Using one compromised system to reach another system.

LATERAL MOVEMENT
Moving between systems inside an environment after
initial access.

HIGH-VALUE ASSET
A system, account, or collection of data whose compromise
could cause serious harm.

DEFENCE IN DEPTH
Using multiple layers of security so that one failed control
does not expose the entire environment.

ATTACK SURFACE
All possible points that an attacker may target.

PATCH
A software update that fixes a problem or vulnerability.

ANTIVIRUS
Software that detects and blocks malicious files
and programs.

ENDPOINT PROTECTION
Security software that monitors endpoint files, processes,
connections, login activity, and behaviour.

FIREWALL
A system that allows or blocks network traffic using rules.

DEFAULT DENY
Blocking access or traffic unless it is specifically allowed.

INBOUND TRAFFIC
Network traffic entering an environment.

OUTBOUND TRAFFIC
Network traffic leaving an environment.

HTTPS
Encrypted communication between a browser and web server.

SOC
Security Operations Centre.

TRIAGE
The initial investigation used to determine the seriousness
and validity of a security alert.

THREAT INTELLIGENCE
Research about attackers, malware, vulnerabilities,
techniques, and threat trends.

DIGITAL FORENSICS
The collection and examination of digital evidence.

INCIDENT RESPONSE
The process of detecting, containing, removing,
and recovering from a security incident.

DFIR
Digital Forensics and Incident Response.
```

---

# Complete Room Summary

```text
1. Identify what needs to be protected.
2. Map devices, users, servers, networks, and data.
3. Define the authorized security scope.
4. Gain visibility through logs, alerts, and traffic.
5. Understand normal activity.
6. Recognize suspicious behaviour.
7. Anticipate realistic attack paths.
8. Prioritize high-value systems.
9. Reduce the attack surface.
10. Apply layered security controls.
11. Prevent attacks where possible.
12. Detect attacks that bypass prevention.
13. Mitigate immediate damage.
14. Analyze what happened.
15. Recover affected systems.
16. Improve security controls continuously.
17. Use defensive knowledge to become a stronger
    penetration tester and future red teamer.
```

---

# Pre Security Path Milestone

Completing this room marked the completion of the **TryHackMe Pre Security path**.

The path provided foundational knowledge in:

* Computer systems
* Hardware
* Networking
* The internet
* DNS
* HTTP and websites
* Operating systems
* Windows
* Linux
* Command-line interfaces
* Virtualization
* Cloud computing
* Programming fundamentals
* Python
* JavaScript
* Databases and SQL
* The CIA triad
* Cryptography concepts
* Offensive security
* Defensive security

The next stage is to continue building practical offensive-security knowledge through **Cyber Security 101**, followed by the **Jr Penetration Tester** path.

---

# Main Takeaway

Defensive security requires understanding the environment, anticipating how connected systems could be attacked, monitoring activity, applying layered protections, detecting threats, limiting damage, investigating incidents, and continuously improving security.

Although my main direction is penetration testing and eventually red teaming, understanding defensive security will help me recognize how attacks are detected, understand client risk, and produce more useful security findings and recommendations.
