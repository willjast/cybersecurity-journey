# Day 6 – HTTP Status Codes, Headers & Cookies

## Topics Covered

- HTTP Status Codes
- HTTP Headers
- Cookies
- Making HTTP Requests

---

# HTTP Status Codes

HTTP status codes tell the client (browser) the result of a request.

---

## Status Code Ranges

| Range | Meaning |
|---|---|
| 100-199 | Information |
| 200-299 | Success |
| 300-399 | Redirects |
| 400-499 | Client Errors |
| 500-599 | Server Errors |

---

# Common HTTP Status Codes

| Code | Meaning |
|---|---|
| 200 | OK / Success |
| 201 | Created |
| 301 | Permanent Redirect |
| 302 | Temporary Redirect |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 405 | Method Not Allowed |
| 500 | Internal Server Error |
| 503 | Service Unavailable |

---

# Important Differences

## 401 Unauthorized
You must log in or authenticate first.

---

## 403 Forbidden
You are not allowed access even if logged in.

---

## 404 Not Found
The page or resource does not exist.

---

## 500 Internal Server Error
The server encountered an internal problem.

---

# HTTP Headers

Headers are extra pieces of information sent between the client and the server.

---

# Common Request Headers

| Header | Purpose |
|---|---|
| Host | Specifies target website |
| User-Agent | Browser/software information |
| Content-Length | Size of data being sent |
| Accept-Encoding | Compression methods supported |
| Cookie | Stores user/session information |

---

# Common Response Headers

| Header | Purpose |
|---|---|
| Set-Cookie | Sends cookie to browser |
| Cache-Control | Controls browser caching |
| Content-Type | Type of data returned |
| Content-Encoding | Compression method used |

---

# Cookies

Cookies are small pieces of data stored in the browser.

Cookies help websites:
- remember users
- keep users logged in
- save preferences
- manage sessions

---

# Example Cookie Flow

1. User logs into website

2. Server sends:
```http
Set-Cookie: session=abc123
```

3. Browser stores cookie

4. Browser sends cookie back on future requests

5. Server recognizes the user

---

# Important Concept

HTTP is stateless.

This means:
- the server does not automatically remember previous requests

Cookies help maintain user sessions.

---

# Making HTTP Requests

HTTP requests can be viewed using:
- browser developer tools
- network tab
- tools like curl

---

# Example Request

```http
GET / HTTP/1.1
Host: tryhackme.com
```

---

# Example Response

```http
HTTP/1.1 200 OK
Content-Type: text/html
```

---

# Useful Commands

## View webpage with curl

```bash
curl https://tryhackme.com
```

---

## View only headers

```bash
curl -I https://tryhackme.com
```

---

# Key Takeaways

- HTTP status codes show request results.
- Headers contain extra request/response information.
- Cookies allow websites to remember users.
- HTTP itself is stateless.
- Browser and server communicate using requests and responses.
