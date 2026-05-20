# Day 11 - Computer Types and Client-Server Basics

## What I Studied

### Computer Types
- Laptop
- Desktop
- Workstation
- Server
- Smartphone
- Tablet
- IoT devices
- Embedded systems

### Client-Server Basics
- Client-server model
- HTTP communication
- HTTP GET requests
- Request and response flow
- DNS
- Ports
- Protocols
- Browser Developer Tools

---

## What I Learned

- Different computer types are designed for different purposes and tradeoffs.
- Laptops prioritize portability while desktops prioritize sustained performance and cooling.
- Workstations focus on reliability and precision for professional workloads.
- Servers provide services to multiple systems over a network.
- IoT devices are network-connected systems designed for specific tasks.
- Embedded systems are small computers built into other devices.

- In the client-server model, the client initiates requests and the server responds.
- HTTP and HTTPS are stateless protocols.
- Websites use sessions, cookies, and tokens to maintain login state.
- DNS translates domain names into IP addresses.
- Ports identify specific services running on a system.
- Browsers automatically send HTTP requests when loading webpages.

---

## Expanded Understanding

- HTTPS is still stateless even though communication is encrypted.
- Sessions allow servers to recognize authenticated users between requests.
- Session hijacking can allow attackers to impersonate a logged-in user if session cookies are stolen.
- Browser Developer Tools allow inspection of requests, responses, headers, and webpage resources.
- One webpage often generates multiple HTTP requests for HTML, CSS, JavaScript, and images.
- Servers may leak useful information through HTTP headers, such as server software versions.
- IoT and embedded systems greatly expand the cybersecurity attack surface because computers now exist in many everyday devices.

---

## Key Terms

- Client: System requesting a service.
- Server: System providing a service.
- Protocol: Rules used for communication.
- Port: Specific access point for a service.
- DNS: Resolves domain names to IP addresses.
- HTTP: Protocol used for web communication.
- HTTPS: Encrypted version of HTTP.
- Cookie: Small piece of data stored in the browser.
- Session: Server-side tracking of authenticated users.
- Token: Authentication data used between systems.

---

## Key Takeaway

Modern computing depends heavily on client-server communication. Web browsing involves many background requests between clients and servers using protocols such as HTTP and HTTPS. Understanding how requests, sessions, ports, DNS, and web communication work is foundational for cybersecurity and web security analysis.
