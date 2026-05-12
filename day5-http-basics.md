# Day 5 – HTTP Basics

## Topics Covered

- What is HTTP and HTTPS
- Requests and responses
- URL structure
- HTTP methods

---

## What is HTTP?

HTTP stands for HyperText Transfer Protocol.

HTTP is the communication method used between a browser and a web server to transfer webpages, images, videos, and other website data.

Example:

Browser → sends request  
Server → sends response

HTTP uses port 80 by default.

---

## What is HTTPS?

HTTPS is the secure version of HTTP.

HTTPS encrypts the data being sent and received, protecting:
- passwords
- login information
- personal data

HTTPS uses port 443 by default.

---

## HTTP vs HTTPS

| HTTP | HTTPS |
|---|---|
| Not encrypted | Encrypted |
| Less secure | Secure |
| Port 80 | Port 443 |

---

## URL Structure

Example URL:

```text
http://user:password@tryhackme.com:80/view-room?id=1#task3
```

### URL Parts

- Scheme = http / https
- Host = domain or IP address
- Port = connection port
- Path = requested page/resource
- Query String = extra information
- Fragment = location on webpage

---

## Making an HTTP Request

Basic request:

```http
GET / HTTP/1.1
```

Meaning:
- GET = request data
- / = homepage
- HTTP/1.1 = protocol version

---

## Example HTTP Request

```http
GET / HTTP/1.1
Host: tryhackme.com
User-Agent: Firefox
Referer: https://google.com
```

### Important Headers

- Host = target website
- User-Agent = browser information
- Referer = previous webpage visited

---

## Example HTTP Response

```http
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 98
```

### Response Breakdown

- 200 OK = successful request
- Content-Type = type of file returned
- Content-Length = size of response

---

## HTTP Methods

### GET
Used to retrieve data from a server.

### POST
Used to send or create data.

### PUT
Used to update existing data.

### DELETE
Used to remove data.

---

## Key Takeaways

- HTTP allows browsers and web servers to communicate.
- HTTPS encrypts communication securely.
- Browsers send requests and servers send responses.
- URLs tell browsers where and how to connect.
- HTTP methods define actions like GET and POST.
