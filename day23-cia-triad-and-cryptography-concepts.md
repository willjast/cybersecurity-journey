# Day 23 – CIA Triad and Cryptography Concepts

## TryHackMe Rooms

1. The CIA Triad — Completed
2. Cryptography Concepts — In Progress

---

# Room 1 – The CIA Triad

## Room Summary

Today I completed the TryHackMe room **The CIA Triad**.

This room marked my first step into the cybersecurity section of the learning path. I learned what cybersecurity actually protects and how security professionals use the CIA Triad to assess systems and incidents.

The CIA Triad consists of:

* Confidentiality
* Integrity
* Availability

These three principles form one of the main foundations of cybersecurity.

---

## What Cybersecurity Protects

Cybersecurity does more than stop attacks or install security software.

It protects digital information by ensuring that:

* unauthorized people cannot access sensitive information
* unauthorized people cannot modify information
* authorized users can access systems and data when needed

A secure system should keep information:

```text
Private
Accurate
Accessible
```

---

# Confidentiality

Confidentiality ensures that sensitive information is only available to authorized people.

## Main Question

```text
Who is allowed to see or access this information?
```

## Examples

* passwords should not be exposed
* medical records should only be available to authorized staff
* private company documents should only be accessible to employees who need them
* personal documents should not be publicly available online
* login credentials should not be written on visible sticky notes

## Confidentiality Breach

A confidentiality breach happens when an unauthorized person sees or accesses information.

Examples:

* someone steals login credentials
* private emails are exposed
* customer records are leaked
* an employee accesses files unrelated to their work

## Common Protections

* strong passwords
* multi-factor authentication
* encryption
* access controls
* file permissions
* locked devices

## Memory Line

```text
Confidentiality = Keep information private
```

---

# Integrity

Integrity ensures that information remains accurate, complete, and trustworthy.

Data should only be changed through an authorized process.

## Main Question

```text
Has the information been changed without permission?
```

## Examples

* bank account details should not be altered
* student grades should not be secretly changed
* system logs should not be deleted to hide activity
* product prices should not be changed before checkout
* attendance records should not be modified after being locked

## Authorized Changes

Integrity does not mean information can never change.

A change is acceptable when it is properly authorized.

Examples:

```text
Teacher officially corrects a grade = integrity maintained

Student secretly changes a grade = integrity breached
```

## Common Protections

* permissions
* hashes
* digital signatures
* audit logs
* backups
* version history
* approval processes

## Memory Line

```text
Integrity = Keep information correct and trustworthy
```

---

# Availability

Availability ensures that systems, services, and information are accessible to authorized users when needed.

## Main Question

```text
Can authorized users access the system or data when they need it?
```

## Examples

* websites should remain online during business hours
* hospital systems should work during emergencies
* employees should be able to access required work systems
* banking services should remain available
* backup systems should take over when the main system fails

## Availability Breach

Availability is affected when authorized users cannot access a service or system.

Examples:

* a website goes offline
* a server crashes
* a network connection fails
* users are locked out
* a denial-of-service attack overwhelms a website
* a software installation disrupts critical services

## Common Protections

* backups
* redundant servers
* backup power
* load balancing
* traffic filtering
* monitoring
* disaster recovery plans
* regular maintenance

## Memory Line

```text
Availability = Keep systems and information accessible
```

---

# CIA Triad Cheat Sheet

```text
CIA = Confidentiality, Integrity, Availability
```

| Principle       | Main Purpose                 | Main Question                   |
| --------------- | ---------------------------- | ------------------------------- |
| Confidentiality | Prevent unauthorized access  | Who can see it?                 |
| Integrity       | Prevent unauthorized changes | Can the data be trusted?        |
| Availability    | Keep services accessible     | Can authorized users access it? |

## Fast Memory Trick

```text
Confidentiality = Private
Integrity = Correct
Availability = Accessible
```

## Incident Identification

```text
Data exposed = Confidentiality

Data modified = Integrity

System unavailable = Availability
```

---

# The Security Mindset

The CIA Triad is not only a group of definitions. It is also a way for cybersecurity professionals to think about security.

When an incident happens, security professionals ask:

```text
Was sensitive information exposed?

Was information changed without permission?

Were systems or services unavailable?
```

These questions help identify the impact of an incident and determine the proper response.

---

## Example Incident

Suppose an attacker accesses a school system and:

* reads private student records
* changes several grades
* shuts down the school website

The incident affects all three CIA principles:

```text
Private records read = Confidentiality

Grades changed = Integrity

Website shut down = Availability
```

One cybersecurity incident can affect one, two, or all three parts of the CIA Triad.

---

## Thinking Like a SOC Analyst

If a SOC analyst notices that an unknown person logged into an employee account, the analyst might ask:

### Confidentiality

* Did the intruder read emails?
* Did they access customer information?
* Did they download private files?

### Integrity

* Did they change files?
* Did they modify account permissions?
* Did they delete security logs?

### Availability

* Did they disable accounts?
* Did they stop services?
* Did they prevent employees from working?

The CIA Triad gives the analyst a structure for investigating the incident.

---

## Personal Takeaway From the CIA Triad Room

The CIA Triad explains what cybersecurity protects:

```text
Is the information private?

Is the information accurate?

Is the information accessible?
```

Understanding these three questions will help me assess security incidents and understand many future cybersecurity concepts.

---

# Room 2 – Cryptography Concepts

## Progress

This room is still in progress.

Today I completed the introduction and learned about symmetric encryption.

---

# Introduction to Cryptography

## What Is Cryptography?

Cryptography is the use of mathematical techniques to protect information.

It can help:

* keep information secret
* detect unauthorized changes
* confirm identities
* protect information while it travels across networks
* protect stored files and data

In simple terms:

```text
Cryptography = protecting information by transforming it into a secure form
```

---

## Why Cryptography Matters

Information sent over the internet does not usually travel directly from the sender to the recipient.

It passes through networking equipment such as:

```text
Computer
→ router
→ internet service provider
→ internet routers
→ destination server
```

Without protection, someone with access to part of that path might attempt to read or modify the information.

Cryptography helps protect:

```text
Confidentiality = prevents unauthorized reading

Integrity = helps detect unauthorized changes
```

Cryptography does not directly guarantee availability because encrypted data or services can still be blocked, deleted, or taken offline.

---

# Core Cryptography Terms

## Plaintext

Plaintext is the original readable information.

Examples:

```text
HELLO
```

```text
Patient name: Alice Smith
```

Plaintext can include:

* text
* passwords
* images
* videos
* files
* medical records
* payment information

---

## Ciphertext

Ciphertext is the scrambled output created by encryption.

Example:

```text
KHOOR
```

Ciphertext should appear meaningless to someone who does not have the correct key.

---

## Encryption

Encryption transforms readable plaintext into unreadable ciphertext.

```text
Plaintext → Encryption → Ciphertext
```

---

## Decryption

Decryption transforms ciphertext back into readable plaintext.

```text
Ciphertext → Decryption → Plaintext
```

---

## Algorithm

An algorithm is the set of rules or instructions used to encrypt and decrypt information.

In modern cryptography, algorithms are normally public and tested by security experts.

Security should not depend on hiding how the algorithm works.

```text
Algorithm = the method or lock design
```

---

## Key

A key is the secret value used by the cryptographic algorithm.

```text
Key = the specific value that locks or unlocks the data
```

A simple analogy is:

```text
Algorithm = how the lock works

Key = the specific metal key used to operate it
```

The algorithm may be publicly known, but the key must remain protected.

---

# Basic Encryption Process

```text
Plaintext + algorithm + key
              ↓
           Encryption
              ↓
          Ciphertext
```

To reverse the process:

```text
Ciphertext + algorithm + correct key
               ↓
            Decryption
               ↓
            Plaintext
```

---

# Symmetric Encryption

Symmetric encryption uses the same shared secret key to encrypt and decrypt data.

```text
Same key encrypts

Same key decrypts
```

Both the sender and receiver need a copy of the same key.

Everyone else must be prevented from obtaining it.

---

# The Lockbox Analogy

Suppose Alice wants to send Bob a secret letter.

1. Alice writes the readable letter.
2. She places it inside a lockbox.
3. She locks the box using a key.
4. She sends the locked box through the public postal system.
5. Bob uses his copy of the same key to unlock it.

| Lockbox Example   | Cryptography Term |
| ----------------- | ----------------- |
| Letter            | Plaintext         |
| Locked box        | Ciphertext        |
| Lock design       | Algorithm         |
| Metal key         | Secret key        |
| Locking the box   | Encryption        |
| Unlocking the box | Decryption        |

Someone may intercept the locked box, but without the correct key, they should not be able to read the message.

---

# Caesar Cipher

The Caesar cipher is a simple historical encryption method.

It shifts each letter through the alphabet by a fixed number of positions.

That number is the key.

## Key of 3

```text
A → D
B → E
C → F
```

At the end of the alphabet, the letters wrap around:

```text
X → A
Y → B
Z → C
```

---

## Encrypting HELLO

Using a key of 3:

```text
H → K
E → H
L → O
L → O
O → R
```

Result:

```text
HELLO → KHOOR
```

In this example:

```text
HELLO = plaintext

KHOOR = ciphertext

3 = key

Shifting letters = algorithm
```

---

## Decrypting KHOOR

To decrypt, move each letter backwards by 3:

```text
K → H
H → E
O → L
O → L
R → O
```

Result:

```text
KHOOR → HELLO
```

---

# Why the Caesar Cipher Is Insecure

The Caesar cipher only has 25 useful shift keys.

An attacker could try every possible shift:

```text
Shift 1
Shift 2
Shift 3
...
Shift 25
```

Trying every possible key is called brute forcing.

A computer can test all Caesar cipher keys almost instantly.

Therefore:

```text
Caesar cipher = useful for learning

Caesar cipher = not secure for real-world use
```

---

# Modern Symmetric Encryption

A major modern symmetric encryption algorithm is:

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

AES is much more complex and secure than the Caesar cipher, but the basic idea remains:

```text
Plaintext + algorithm + secret key → ciphertext
```

---

# Benefits of Symmetric Encryption

Symmetric encryption is:

* fast
* efficient
* suitable for large amounts of data

It is commonly used for:

* file encryption
* full-disk encryption
* backups
* database data
* network traffic
* web session traffic

---

# The Key Distribution Problem

The main weakness of symmetric encryption is safely sharing the secret key.

Both Alice and Bob need the same key, but sending it openly would allow an attacker to intercept it.

```text
Symmetric encryption works well after the key is shared.

The difficult part is securely sharing the key.
```

This is known as the:

```text
Key distribution problem
```

Asymmetric cryptography, which I will learn next, helps solve this problem.

---

# Important Key Security Lesson

Even a strong encryption algorithm becomes ineffective if the secret key is stolen.

```text
Strong encryption + exposed key = broken confidentiality
```

The algorithm can be excellent, but an attacker with the key may be able to decrypt the protected information.

---

# Symmetric Encryption Cheat Sheet

## Core Terms

```text
Plaintext = original readable information

Ciphertext = scrambled encrypted information

Encryption = plaintext into ciphertext

Decryption = ciphertext back into plaintext

Algorithm = rules used to transform the information

Key = secret value used by the algorithm
```

## Symmetric Encryption

```text
One shared secret key

Same key encrypts and decrypts

Both parties need the key

The key must remain secret
```

## Caesar Cipher

```text
Algorithm = shift alphabet letters

Key = number of positions shifted

Key 3:

HELLO → KHOOR
```

## Advantages

```text
Fast

Efficient

Good for large amounts of data
```

## Main Challenge

```text
Key distribution problem:

How do both parties safely receive the same secret key?
```

## Modern Example

```text
AES = Advanced Encryption Standard
```

---

# Connection Between Today’s Rooms

The two rooms connect directly.

The CIA Triad explains what needs protection:

```text
Confidentiality
Integrity
Availability
```

Cryptography provides practical tools that help protect:

```text
Confidentiality by preventing unauthorized reading

Integrity by helping detect unauthorized changes
```

Symmetric encryption is especially useful for keeping large amounts of information confidential because it is fast and efficient.

---

# Day 23 Personal Takeaway

Today I completed the CIA Triad room and began learning cryptography.

I learned that cybersecurity protects information by keeping it:

```text
Private
Accurate
Accessible
```

I also learned that encryption changes readable plaintext into unreadable ciphertext using an algorithm and a key.

The most important symmetric encryption idea is:

```text
The same secret key encrypts and decrypts the information.
```

Symmetric encryption is fast, but safely distributing the shared key is its main challenge.

I will continue the Cryptography Concepts room in my next study session.
