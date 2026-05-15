# Day 8 — JavaScript, DevTools, and Web Security

## Topics Covered
- JavaScript fundamentals
- Browser DevTools
- DOM manipulation
- Sensitive Data Exposure
- HTML Injection
- Source code inspection
- Frontend security concepts

---

# JavaScript Fundamentals

JavaScript is used to make websites interactive and dynamic.

## Key Concepts
- HTML provides structure
- CSS controls styling
- JavaScript controls behaviour and interactivity

JavaScript can:
- respond to clicks and events
- change webpage content dynamically
- modify page styling
- update webpages without refreshing

---

# JavaScript Examples Learned

## Changing HTML Content

```javascript
document.getElementById("demo").innerHTML = "Hack the Planet";
```

This changes the content of an HTML element with the ID `demo`.

---

## Button Click Event

```html
<button onclick='document.getElementById("demo").innerHTML = "Button Clicked";'>
Click Me!
</button>
```

This executes JavaScript when the button is clicked.

---

# DevTools Practice

Used browser Developer Tools (F12) to inspect and manipulate webpages.

## DevTools Tabs Explored
- Elements
- Console
- Source Code

---

# JavaScript Commands Practiced

## Alert Popup

```javascript
alert("Hello");
```

Creates a popup message in the browser.

---

## Changing Background Colour

```javascript
document.body.style.background="red";
```

Changed webpage background colour dynamically.

Also tested:
- black background
- different styles

---

## Replacing Entire Page Content

```javascript
document.body.innerHTML="WEBSITE HACKED";
```

Replaced the visible webpage content locally in the browser.

---

## Modifying HTML Headings

```javascript
document.querySelector("h1").innerHTML = "Cybersecurity Student";
```

Changed the content of the first `<h1>` element on the page.

---

# Source Code and Inspection

Learned the difference between:

## View Page Source
Shows the original HTML sent from the server.

## Inspect Element
Shows the live DOM after JavaScript changes.

---

# Important Frontend Security Concepts

## Frontend Code Is Visible
Users can inspect:
- HTML
- CSS
- JavaScript
- hidden fields
- comments
- page structure

Frontend code should never contain secrets.

---

# Sensitive Data Exposure

Sensitive Data Exposure happens when websites accidentally expose private information.

## Examples
- credentials in comments
- hidden admin links
- API keys
- developer notes
- hidden form fields

---

# Key Lesson

Anything sent to the browser can potentially be viewed by users or attackers.

---

# HTML Injection

HTML Injection happens when user input is displayed without sanitisation.

## Example

```html
<h1>Hello</h1>
```

If rendered directly by the browser, the input becomes actual HTML instead of harmless text.

---

# Security Risks of HTML Injection
- page manipulation
- fake forms
- phishing
- malicious content injection
- possible transition into XSS vulnerabilities

---

# Important Security Principle

Never trust user input.

User input should always be:
- validated
- sanitised
- treated as potentially malicious

---

# Main Takeaways

Today I learned:
- how JavaScript interacts with webpages
- how browsers execute JavaScript
- how DevTools can manipulate webpages locally
- how page source differs from live DOM inspection
- how frontend vulnerabilities occur
- why input sanitisation is important in web security

I also practiced hands-on JavaScript execution and webpage manipulation using browser DevTools.
