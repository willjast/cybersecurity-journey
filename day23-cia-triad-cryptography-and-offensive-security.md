# Day 23 – CIA Triad, Cryptography, and Offensive Security

## TryHackMe Rooms Completed

1. The CIA Triad
2. Cryptography Concepts
3. Become a Hacker

---

# Day Summary

Today I moved from general computer fundamentals into core cybersecurity concepts.

I learned:

* what cybersecurity protects through the CIA Triad
* how cryptography protects digital information
* the difference between symmetric and asymmetric encryption
* how HTTPS uses certificates and hybrid encryption
* what offensive security and ethical hacking are
* how attackers enumerate web applications
* how weaknesses can be chained together
* how Gobuster and Hydra automate parts of security testing
* why permission and scope are essential during penetration testing

I also installed Gobuster on my local Linux environment and used it against my own authorized website to practise web-content enumeration.

---

# Room 1 – The CIA Triad

## What Is the CIA Triad?

The CIA Triad describes the three main properties cybersecurity protects:

```text
Confidentiality
Integrity
Availability
```

A secure system should keep information:

```text
Private
Accurate
Accessible
```

---

## Confidentiality

Confidentiality ensures that sensitive information is only accessible to authorized users.

### Main Question

```text
Who is allowed to see or access this information?
```

### Examples

* passwords should not be exposed
* medical records should only be available to authorized staff
* internal company documents should not be publicly accessible
* private emails should not be read by unauthorized users

### Common Protections

* passwords
* multi-factor authentication
* encryption
* access controls
* file permissions

### Memory Line

```text
Confidentiality = Keep information private
```

---

## Integrity

Integrity ensures that data remains accurate, complete, and trustworthy.

Data should only be changed through an authorized process.

### Main Question

```text
Has the information been changed without permission?
```

### Examples

* grades should not be secretly modified
* bank-transfer details should not be altered
* product prices should not be changed before checkout
* security logs should not be deleted to hide activity

### Common Protections

* permissions
* hashes
* digital signatures
* audit logs
* backups
* approval processes

### Memory Line

```text
Integrity = Keep information accurate and trustworthy
```

---

## Availability

Availability ensures that authorized users can access systems and information when needed.

### Main Question

```text
Can authorized users access the system when they need it?
```

### Examples

* websites should remain online during business hours
* hospital systems should work during emergencies
* employees should be able to access work systems
* backup systems should take over after failures

### Common Protections

* backups
* redundant systems
* backup power
* monitoring
* traffic filtering
* load balancing
* disaster-recovery planning

### Memory Line

```text
Availability = Keep systems and information accessible
```

---

## CIA Triad Cheat Sheet

| Principle       | Purpose                           | Main Question                   |
| --------------- | --------------------------------- | ------------------------------- |
| Confidentiality | Prevent unauthorized access       | Who can see it?                 |
| Integrity       | Prevent unauthorized modification | Can it be trusted?              |
| Availability    | Maintain reliable access          | Can authorized users access it? |

```text
Information exposed = Confidentiality affected

Information modified = Integrity affected

Service unavailable = Availability affected
```

---

## The Security Mindset

The CIA Triad is not only a group of definitions. It is also a framework security professionals use when investigating incidents.

They ask:

```text
Was sensitive information exposed?

Was information changed without permission?

Were systems or services unavailable?
```

A single incident may affect one, two, or all three parts of the CIA Triad.

---

# Room 2 – Cryptography Concepts

## What Is Cryptography?

Cryptography uses mathematical techniques to protect information.

It supports:

* confidentiality
* integrity
* authentication
* secure communication
* tamper detection

Cryptography is used when protecting:

* web traffic
* passwords
* banking information
* medical records
* files
* messages
* digital identities

---

## Core Cryptography Terms

### Plaintext

Plaintext is the original readable information.

Example:

```text
HELLO
```

### Ciphertext

Ciphertext is the scrambled output created by encryption.

Example:

```text
KHOOR
```

### Encryption

Encryption transforms plaintext into ciphertext.

```text
Plaintext → Encryption → Ciphertext
```

### Decryption

Decryption transforms ciphertext back into plaintext.

```text
Ciphertext → Decryption → Plaintext
```

### Algorithm

An algorithm is the method or set of rules used to transform information.

```text
Algorithm = how the lock works
```

Algorithms are normally public and tested by security experts.

### Key

A key is the value that controls the cryptographic process.

```text
Key = the specific value that operates the lock
```

Security should depend on protecting the key rather than hiding the algorithm.

---

## Basic Cryptographic Process

```text
Plaintext + algorithm + key
              ↓
           Encryption
              ↓
          Ciphertext
```

```text
Ciphertext + algorithm + correct key
               ↓
            Decryption
               ↓
            Plaintext
```

---

# Symmetric Encryption

Symmetric encryption uses one shared secret key.

```text
The same key encrypts.

The same key decrypts.
```

Both parties must have a copy of the key, and nobody else should obtain it.

## Lockbox Analogy

| Lockbox Example   | Cryptography Term |
| ----------------- | ----------------- |
| Letter            | Plaintext         |
| Locked box        | Ciphertext        |
| Lock design       | Algorithm         |
| Metal key         | Secret key        |
| Locking the box   | Encryption        |
| Unlocking the box | Decryption        |

---

## Caesar Cipher

The Caesar cipher shifts letters by a fixed number of positions.

That number is the key.

Using a key of `3`:

```text
A → D
B → E
C → F
```

Example:

```text
HELLO → KHOOR
```

To decrypt it, each letter is shifted backwards by three.

```text
KHOOR → HELLO
```

The Caesar cipher is useful for learning but not secure for real systems because it only has a small number of possible keys.

---

## Modern Symmetric Encryption

A major modern symmetric algorithm is:

```text
AES
```

AES stands for:

```text
Advanced Encryption Standard
```

Common AES key sizes include:

```text
128 bits
192 bits
256 bits
```

Symmetric encryption is:

* fast
* efficient
* suitable for large quantities of data

It is commonly used for:

* network traffic
* file encryption
* full-disk encryption
* backups
* web-session traffic

---

## The Key Distribution Problem

The main challenge with symmetric encryption is safely sharing the secret key.

```text
Symmetric encryption works well after the key is shared.

The challenge is sharing that key securely.
```

If the key is sent openly, an attacker may intercept it.

This is called the:

```text
Key distribution problem
```

---

# Asymmetric Encryption

Asymmetric encryption uses two mathematically linked keys:

```text
Public key
Private key
```

## Public Key

The public key can be shared openly.

## Private Key

The private key must remain secret with its owner.

For confidential communication:

```text
Encrypt with the recipient's public key.

Decrypt with the recipient's private key.
```

---

## Mailbox Analogy

```text
Public key = public mail slot

Private key = owner's mailbox key
```

Anyone can put a letter through the mail slot, but only the owner can unlock the mailbox and retrieve the letters.

This allows someone to receive protected information without first sharing a secret key.

---

## Digital Signatures

Asymmetric cryptography is also used for digital signatures.

```text
Private key creates a signature.

Public key verifies the signature.
```

Digital signatures help provide:

* authenticity
* integrity
* evidence that information was not altered

They do not primarily hide information.

---

# Symmetric vs Asymmetric Encryption

| Feature        | Symmetric                        | Asymmetric                                       |
| -------------- | -------------------------------- | ------------------------------------------------ |
| Number of keys | One shared secret key            | Public and private key pair                      |
| Speed          | Fast                             | Slower                                           |
| Key sharing    | Secret key must be shared safely | Public key can be shared openly                  |
| Main use       | Bulk-data encryption             | Authentication, key establishment and signatures |
| Example        | AES                              | RSA or elliptic-curve cryptography               |
| Analogy        | One key locks and unlocks a box  | Public mailbox with private door key             |

---

# HTTPS and Hybrid Encryption

HTTPS combines symmetric and asymmetric cryptography.

A simplified process is:

```text
1. Browser connects to the website.
2. Website provides its certificate.
3. Browser validates the certificate.
4. Asymmetric cryptography helps establish shared secrets.
5. Symmetric session keys are derived.
6. Symmetric encryption protects the browsing traffic.
```

This is called a hybrid approach.

```text
Asymmetric cryptography = secure setup and authentication

Symmetric encryption = fast protection of session data
```

---

## Digital Certificates

A digital certificate connects a domain identity with a public key.

A certificate includes information such as:

* domain name
* public key
* certificate issuer
* valid-from date
* expiration date
* digital signature

A Certificate Authority signs the certificate.

The browser checks:

* whether the certificate is trusted
* whether the domain matches
* whether it is still valid
* whether it has been altered

---

## What the Browser Padlock Means

The padlock generally means:

* the site is using HTTPS
* the browser accepted the certificate
* traffic is encrypted
* tampering during transmission can usually be detected

It does not prove:

* that the website is honest
* that it is not a scam
* that all downloads are safe
* that the website handles information responsibly

```text
The padlock protects the connection, not the reputation of the website.
```

---

## Cryptography Cheat Sheet

```text
Plaintext = readable information

Ciphertext = encrypted information

Encryption = plaintext into ciphertext

Decryption = ciphertext into plaintext

Algorithm = cryptographic method

Key = value controlling the method
```

```text
Symmetric = one shared secret key

Asymmetric = public and private key pair

Hybrid = asymmetric setup plus symmetric speed
```

---

# Room 3 – Become a Hacker

## What Is Offensive Security?

Offensive security involves testing systems from an attacker's perspective to identify weaknesses before malicious attackers exploit them.

```text
Offensive security = safely testing systems to improve their security
```

Offensive testing must be:

* authorized
* legal
* controlled
* documented
* limited to an agreed scope

---

## The Hacker Mindset

A security tester asks:

```text
What is exposed?

What can be accessed?

What does the system trust?

What happens with unexpected input?

Can multiple weaknesses be chained together?
```

A basic methodology is:

```text
Observe
Question
Test
Analyze
Document
Recommend fixes
```

Ethical hacking is not random breaking. It is structured and methodical testing.

---

# Core Offensive Security Terminology

## Scope

Scope defines which systems and actions are permitted during an assessment.

```text
Scope = legal and technical testing boundaries
```

It identifies:

* approved systems
* permitted techniques
* excluded systems
* allowed testing times
* prohibited actions

---

## Vulnerability

A vulnerability is a weakness in software, hardware, configuration, or process that could create security risk.

Examples:

* weak password
* outdated software
* broken access control
* publicly exposed sensitive page
* incorrect permissions

```text
Vulnerability = the weakness
```

---

## Exploit

An exploit is a method used to take advantage of a vulnerability.

```text
Exploit = using the weakness
```

Example:

```text
Vulnerability:
An administrator account uses a weak password.

Exploit:
Testing common passwords and gaining access.
```

---

## Enumeration

Enumeration is the systematic collection of detailed information about a target.

Examples include identifying:

* pages
* directories
* files
* users
* services
* software versions
* network shares

```text
Enumeration = discovering what exists
```

---

## Credentials

Credentials are information used to prove identity.

Examples:

* username and password
* security token
* certificate
* API key
* smart card

---

## Authentication

Authentication verifies identity.

```text
Authentication = Who are you?
```

Authorization determines what an authenticated user may do.

```text
Authorization = What are you allowed to do?
```

---

## Dictionary Attack

A dictionary attack tests possible credentials from a prepared wordlist.

```text
Dictionary attack = trying likely values from a list
```

It differs from brute force, which attempts every possible combination.

---

# Red Teaming vs Penetration Testing

## Penetration Test

A penetration test focuses on identifying and validating vulnerabilities within an agreed scope.

## Red Teaming

Red teaming simulates a realistic adversary to test an organization's:

* prevention
* detection
* incident response
* employee awareness
* security controls

```text
Pentest = find and validate weaknesses

Red team = simulate a realistic attacker and test the defenders
```

---

# Finding Hidden Web Content

In the lab, I tested possible website paths manually.

Examples included:

```text
/sitemap
/mail
/register
/login
/admin
```

A page may not be linked on the homepage but can still be accessible by entering its address directly.

Important lesson:

```text
Not linked does not mean protected.
```

Sensitive pages require authentication and authorization. Renaming or hiding a page is not proper access control.

---

## HTTP Status Codes Reviewed

```text
200 = request succeeded

301 or 302 = redirect

403 = resource exists but access is forbidden

404 = resource was not found
```

A `403` response may still reveal that a resource exists.

---

# Gobuster

Gobuster automates web-content enumeration by testing names from a wordlist.

TryHackMe command:

```bash
gobuster dir --url http://www.onlineshop.thm/ -w /usr/share/wordlists/dirbuster/directory-list.txt
```

## Command Breakdown

```text
gobuster = command-line tool

dir = directory-enumeration mode

--url = target website

-w = wordlist
```

A wordlist contains possible directory and file names such as:

```text
admin
login
register
backup
uploads
dashboard
```

Gobuster tests each word as a potential web path.

---

# Local Gobuster Practice

I installed Gobuster in my local Ubuntu environment:

```bash
sudo apt install gobuster
```

The original TryHackMe wordlist path did not exist locally, so I checked the available DIRB wordlists:

```bash
ls /usr/share/dirb/wordlists
```

I found and used:

```text
/usr/share/dirb/wordlists/common.txt
```

I then ran Gobuster against my own website:

```bash
gobuster dir \
-u https://www.jast.mortgage/ \
-w /usr/share/dirb/wordlists/common.txt
```

The scan produced request timeouts because the site or hosting service was responding slowly or limiting the automated requests.

The default settings included:

```text
Threads: 10
Timeout: 10 seconds
```

To reduce the request load, I learned to use:

```bash
gobuster dir \
-u https://www.jast.mortgage/ \
-w /usr/share/dirb/wordlists/common.txt \
-t 1 \
--timeout 30s \
--delay 500ms
```

## Additional Gobuster Options

```text
-t 1 = use one request thread

--timeout 30s = allow more time for each response

--delay 500ms = pause between requests
```

I also learned that testing a small custom wordlist can be better than immediately scanning thousands of possible paths.

Important practical lesson:

```text
Start small and slowly increase the scan.

Automated tools must be adjusted for the target's response and hosting limits.
```

This test was performed only against a website that I own and was therefore authorized.

---

# Chaining Weaknesses

A small weakness may become serious when combined with other weaknesses.

Example attack chain from the lab:

```text
Discoverable login page
+ predictable admin username
+ weak password
+ no effective rate limiting
= unauthorized administrator access
```

This is known as vulnerability chaining.

```text
Small weakness + small weakness + small weakness
= larger security compromise
```

---

# Hydra

Hydra automates login testing against supported services.

TryHackMe command:

```bash
hydra -l admin -P passlist.txt www.onlineshop.thm http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V
```

## Command Breakdown

```text
hydra = tool

-l admin = use one username

-P passlist.txt = use a password wordlist

www.onlineshop.thm = authorized target

http-post-form = login uses an HTTP POST request

/login = login endpoint

^USER^ = username placeholder

^PASS^ = password placeholder

F=incorrect = response indicating failure

-V = verbose output
```

The command tests the username `admin` using each password from the wordlist.

---

## Why the Login Was Vulnerable

The underlying weaknesses included:

* predictable administrator username
* weak password
* repeated attempts permitted
* lack of effective rate limiting
* lack of MFA
* insufficient monitoring or lockout controls

Hydra did not create the weakness. It automated the discovery of an existing weak password.

---

## Defences Against Credential Attacks

* strong and unique passwords
* multi-factor authentication
* rate limiting
* temporary account lockout
* generic login errors
* monitoring and alerting
* restricted administrator access
* blocking commonly used passwords

---

# Connection to the CIA Triad

Compromised administrator access can affect all three principles.

## Confidentiality

The attacker may view private data.

## Integrity

The attacker may modify records, settings, users, or prices.

## Availability

The attacker may delete content, disable accounts, or stop services.

```text
Admin compromise can affect confidentiality, integrity, and availability.
```

---

# Offensive Security Workflow

The room demonstrated this simplified process:

```text
1. Obtain authorization and confirm scope
2. Observe the target
3. Enumerate exposed content
4. Discover an entry point
5. Identify a weakness
6. Test whether the weakness is exploitable
7. Assess the resulting access and impact
8. Document findings
9. Recommend remediation
```

---

# Offensive Security Cheat Sheet

```text
Scope = permitted testing boundaries

Vulnerability = weakness

Exploit = method that uses a weakness

Enumeration = systematic information gathering

Credentials = identity-proving information

Authentication = verifying identity

Authorization = deciding permitted actions

Dictionary attack = testing values from a predefined list
```

```text
Gobuster = web-content enumeration

Hydra = automated credential testing
```

```text
Hidden is not protected.

Automation makes weak security fail faster.

Multiple small weaknesses can create one major attack path.
```

---

# Career Direction and Further Learning

My long-term goal is:

```text
Penetration Tester
→ Red Team Operator
```

My current planned learning route is:

```text
1. Finish Pre Security
2. Complete Cyber Security 101
3. Complete the Jr Penetration Tester path
4. Reinforce web skills through PortSwigger Academy
5. Practise guided systems through Hack The Box Starting Point
6. Build professional-style sanitized penetration-test reports
7. Prepare for a practical entry-level certification such as eJPT
8. Apply for junior pentesting and related security positions
9. Continue learning Active Directory, web and network testing
10. Move toward intermediate certifications and OSCP later
11. Build professional penetration-testing experience
12. Progress toward red teaming
```

Defensive knowledge will still be valuable because an effective penetration tester and red teamer must understand:

* logs
* monitoring
* detection
* incident response
* security controls
* what defenders can observe

However, I will prioritize offensive-security training because penetration testing and red teaming are my main career goals.

---

# Day 23 Final Takeaway

Today connected three major cybersecurity ideas.

The CIA Triad explains what cybersecurity protects:

```text
Confidentiality
Integrity
Availability
```

Cryptography provides tools that help protect information:

```text
Encryption protects confidentiality.

Signatures and integrity checks help detect changes.
```

Offensive security tests whether those protections can be bypassed:

```text
What is exposed?

What can be accessed?

What weaknesses exist?

Can weaknesses be chained together?

What impact would successful exploitation create?
```

The most important ethical rule is:

```text
Only test systems that I own or have explicit permission to assess.

Always remain within the defined scope.
```

Offensive security is not random breaking. It is the authorized, controlled, and documented process of discovering weaknesses so they can be fixed before malicious attackers exploit them.
