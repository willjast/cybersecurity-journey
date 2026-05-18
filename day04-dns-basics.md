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
nslookup -type=A example.com
```

### AAAA Record
Maps a domain name to an IPv6 address.
Example: 2606:4700:20::681a:be5

Example:
```bash
nslookup -type=AAAA example.com
```

### CNAME Record
Points one domain name to another domain name.

Example:
```bash
nslookup -type=CNAME example.com
```

### MX Record
Shows which mail servers handle email for a domain.

Example:
```bash
nslookup -type=MX example.com
```

### TXT Record
Often used for verification, email security, and domain ownership.

Example:
```bash
nslookup -type=TXT example.com
```

---

## Commanmds Practiced

```bash
nslookup example.com
nslookup -type=A example.com
nslookup -type=CNAME example.com
nslookup -type=MX example.com
nslookup -type=TXT example.com
```

## Key Takeaway

DNS translates domain names into IP addresses so devices can locate websites and internet services.




