# Day 4 – DNS Basics

## Topics Covered
- What is DNS?
- Domain hierarchy
- DNS record types
- How DNS requests work
- Practical DNS lookup using nslookup

---

## What is DNS?

DNS stands for Domain Name System.

DNS works like the phonebook of the internet. It translates human-readable domain names into IP addresses.

Example:

google.com → IP address

Computers communicate using IP addresses, but humans remember names better than numbers.

---

## Domain Hierarchy

Domains are organized in levels.

Example:

www.example.com

- .com = Top-Level Domain (TLD)
- example = domain name
- www = subdomain

DNS works from the top down to find the correct IP address.

---

## DNS Record Types

### A Record
Maps a domain name to an IPv4 address.

Example:
```bash
nslookup --type=A example.com
