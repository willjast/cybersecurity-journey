# Day 21 – JavaScript: Simple Demo

## TryHackMe Room

JavaScript: Simple Demo
Explore what a basic JavaScript program looks like.

---

# Topics Covered

## Introduction to JavaScript

Today I completed the **JavaScript: Simple Demo** room.

This room introduced JavaScript as a popular programming language used heavily on websites and web applications.

JavaScript originally ran mainly inside web browsers, but with Node.js, JavaScript can also run outside the browser, including from the command line and on servers.

In this room, I built and studied a simple **Guess the Number** game using JavaScript.

The goal of the program was:

* the computer secretly picks a number
* the user guesses the number
* the program gives feedback
* the user keeps guessing until correct
* the program counts the number of tries

This room followed the same idea as the previous Python room, which helped me compare how Python and JavaScript solve the same problem using different syntax.

---

# JavaScript and Node.js

## What I Learned

JavaScript can run in different places:

* inside a web browser
* in the terminal using Node.js
* on a server using Node.js

In this room, JavaScript was run using Node.js.

To run a JavaScript file from the Linux CLI, I used:

```bash
node filename.js
```

or, for module-style JavaScript files:

```bash
node filename.mjs
```

Example:

```bash
node guess_v3.mjs
```

---

# JavaScript Files

JavaScript files usually use the `.js` extension.

Example:

```text
guess_v1.js
guess_v2.js
guess_v3.js
```

For my own Linux CLI practice, I used:

```text
guess_v3.mjs
```

because the code used `import` statements.

---

# Browser Console Practice

I also learned that JavaScript can be tested inside a browser console.

In Firefox, the developer tools can be opened with:

```text
F12
```

JavaScript can then be written directly in the Console tab.

Example:

```javascript
console.log("Hello from JavaScript");
```

This is useful for understanding how JavaScript runs in browsers.

---

# Variables with let

## What I Learned

JavaScript uses `let` to declare variables whose values can change.

Example:

```javascript
let tries = 0;
let guess = 0;
```

In the guessing game:

```text
tries = number of attempts
guess = the user's current guess
```

Both of these values can change while the program runs, so `let` is used.

---

# Constants with const

JavaScript uses `const` to declare values that should not change.

Example:

```javascript
const secret = Math.floor(Math.random() * 20) + 1;
```

In the guessing game:

```text
secret = the random number the user is trying to guess
```

The secret number should stay the same during one round of the game, so `const` is used.

---

# let vs const

```text
let   = value can change
const = value should stay fixed
```

Examples:

```javascript
let tries = 0;
let guess = 0;
const secret = 12;
```

In this game:

* `tries` changes
* `guess` changes
* `secret` stays the same

---

# Generating a Random Number

The program used:

```javascript
const secret = Math.floor(Math.random() * 20) + 1;
```

This creates a random whole number between 1 and 20.

## Breakdown

```javascript
Math.random()
```

Creates a random decimal between 0 and almost 1.

Example:

```text
0.372
```

```javascript
Math.random() * 20
```

Changes the range to 0 through almost 20.

```javascript
Math.floor()
```

Rounds the decimal down to a whole number.

Example:

```text
7.44 becomes 7
```

```javascript
+ 1
```

Shifts the range from 0–19 to 1–20.

---

# Displaying Output with console.log()

JavaScript uses `console.log()` to display output.

Example:

```javascript
console.log("I'm thinking of a number between 1 and 20");
```

This prints a message to the terminal or browser console.

Python comparison:

```python
print("Hello")
```

JavaScript comparison:

```javascript
console.log("Hello");
```

---

# Getting User Input with readline

In Node.js, getting terminal input is more complex than Python.

The program imported the readline tools:

```javascript
import * as readline from "node:readline/promises";
import { stdin as input, stdout as output } from "node:process";
```

Then it created an input/output interface:

```javascript
const rl = readline.createInterface({ input, output });
```

This allowed the program to ask the user a question and wait for an answer.

---

# Asking the User for a Guess

The program used:

```javascript
const text = await rl.question("Take a guess: ");
```

This asks the user to enter a guess.

The keyword `await` tells JavaScript to pause and wait until the user responds.

The answer is stored as text.

---

# Converting Text to a Number

User input starts as text.

Example:

```text
"10"
```

But the program needs a number:

```text
10
```

So the program uses:

```javascript
guess = parseInt(text, 10);
```

This converts the text into an integer using base 10.

Example:

```javascript
const text = "10";
guess = parseInt(text, 10);
```

Now:

```javascript
guess = 10;
```

---

# Counting Attempts

The program counts every guess using:

```javascript
tries = tries + 1;
```

This means:

```text
Take the current value of tries, add 1, and store it back in tries.
```

Example:

```text
tries = 0
tries = tries + 1
tries = 1
```

---

# Conditional Statements

## What I Learned

Conditional statements allow JavaScript to make decisions.

The program used:

```javascript
if
else if
else
```

These allowed the program to check whether the user’s guess was:

* out of range
* too low
* too high
* correct

---

# Conditional Logic Used

```javascript
if (guess < 1 || guess > 20) {
    console.log("That number is out of range. Try again.");
} else if (guess < secret) {
    console.log("Too low, try again.");
} else if (guess > secret) {
    console.log("Too high, try again.");
} else {
    console.log("You got it in", tries, "tries!");
}
```

---

# Understanding if / else if / else

## if

```javascript
if (guess < 1 || guess > 20) {
```

This checks the first condition.

It asks:

```text
Is the guess less than 1 OR greater than 20?
```

If yes, the guess is out of range.

---

## else if

```javascript
} else if (guess < secret) {
```

This checks another condition only if the previous condition was false.

It checks whether the guess is too low.

---

## another else if

```javascript
} else if (guess > secret) {
```

This checks whether the guess is too high.

---

## else

```javascript
} else {
```

This runs if all previous conditions were false.

If the guess is:

* not out of range
* not too low
* not too high

then it must be correct.

---

# JavaScript OR Operator

JavaScript uses:

```javascript
||
```

to mean OR.

Example:

```javascript
if (guess < 1 || guess > 20) {
```

This means:

```text
If guess is less than 1 OR guess is greater than 20
```

Python comparison:

```python
if guess < 1 or guess > 20:
```

JavaScript comparison:

```javascript
if (guess < 1 || guess > 20) {
```

---

# Comparison Operators

Important operators learned:

```text
<    less than
>    greater than
||   OR
!==  not equal
===  equal
=    assignment
```

Important difference:

```javascript
guess = 10;
```

means assign/store 10 in `guess`.

```javascript
guess === secret
```

means check whether `guess` is equal to `secret`.

---

# Loops / Iteration

## What I Learned

A loop repeats a block of code.

The program used a `while` loop:

```javascript
while (guess !== secret) {
```

This means:

```text
While the guess is not equal to the secret number, keep repeating the code inside the loop.
```

The loop keeps asking the user for guesses until the correct number is entered.

---

# Why the while Loop Is Needed

Without the loop, the program only gives the user one guess.

With the loop, the program repeats:

```text
Ask for a guess
Convert the guess to a number
Add 1 to tries
Check the guess
Give feedback
Repeat if incorrect
```

The loop stops when:

```javascript
guess === secret
```

---

# JavaScript Code Blocks

JavaScript uses curly braces to define code blocks.

Example:

```javascript
while (guess !== secret) {
    // code inside the loop
}
```

Everything inside `{ }` belongs to the loop and repeats.

Python uses indentation for code blocks, but JavaScript uses curly braces.

---

# Full Final JavaScript Program

```javascript
import * as readline from "node:readline/promises";
import { stdin as input, stdout as output } from "node:process";

const rl = readline.createInterface({ input, output });

try {
    const secret = Math.floor(Math.random() * 20) + 1; // 1 <= secret <= 20
    let tries = 0;
    let guess = 0;

    console.log("I'm thinking of a number between 1 and 20");

    while (guess !== secret) {
        const text = await rl.question("Take a guess: ");
        guess = parseInt(text, 10);

        tries = tries + 1;

        if (guess < 1 || guess > 20) {
            console.log("That number is out of range. Try again.");
        } else if (guess < secret) {
            console.log("Too low, try again.");
        } else if (guess > secret) {
            console.log("Too high, try again.");
        } else {
            console.log("You got it in", tries, "tries!");
        }
    }
} finally {
    rl.close();
}
```

---

# Program Flow

```text
1. Import readline tools.
2. Import input and output from node:process.
3. Create the readline interface.
4. Pick a random secret number between 1 and 20.
5. Set tries to 0.
6. Set guess to 0.
7. Print the starting message.
8. Start the while loop.
9. Ask the user for a guess.
10. Convert the input from text to number.
11. Add 1 to tries.
12. Check if the guess is out of range.
13. Check if the guess is too low.
14. Check if the guess is too high.
15. If none of those are true, the guess is correct.
16. Stop when guess equals secret.
17. Close the readline interface.
```

---

# try / finally

The program uses:

```javascript
try {
    // main program
} finally {
    rl.close();
}
```

The `finally` block runs at the end and closes the readline interface.

This is cleanup.

The important cleanup line is:

```javascript
rl.close();
```

This closes the input/output interface so the program can end properly.

---

# Linux CLI Practice

I practiced creating and editing a JavaScript file in Linux.

Commands used:

```bash
mkdir JavaScript-Demo
cd JavaScript-Demo
nano guess_v3.mjs
node guess_v3.mjs
```

I learned that `.mjs` is not a command. It is a file extension.

Correct usage:

```bash
nano guess_v3.mjs
node guess_v3.mjs
```

Incorrect usage:

```bash
.mjs
```

---

# Editing Code in Linux CLI

I practiced editing code using nano.

Command:

```bash
nano guess_v3.mjs
```

Nano save and exit commands:

```text
Ctrl + O  = save
Enter     = confirm filename
Ctrl + X  = exit
```

I also learned that an asterisk `*` at the top of nano means the file has unsaved changes.

---

# Directory Navigation Practice

I practiced Linux navigation commands.

```bash
ls
```

Lists files and folders.

```bash
cd JavaScript-Demo
```

Moves into the JavaScript-Demo folder.

```bash
cd ..
```

Moves up one directory.

I also learned that this is incorrect:

```bash
cd..
```

Linux requires a space:

```bash
cd ..
```

---

# My Own JavaScript Practice

I modified the original guessing game to use a range from 1 to 30 instead of 1 to 20.

I changed the random number line to:

```javascript
const secret = Math.floor(Math.random() * 30) + 1;
```

I also changed the out-of-range condition to:

```javascript
if (guess < 1 || guess > 30) {
```

I updated the message to:

```javascript
console.log("How about a number between 1 and 30. What are you thinking?");
```

This practice helped me understand that when changing the game range, I must update multiple parts of the code:

* the random number generator
* the displayed message
* the range-check condition

---

# My Edited Practice Code

```javascript
import * as readline from "node:readline/promises";
import { stdin as input, stdout as output } from "node:process";

const rl = readline.createInterface({ input, output });

try {
    const secret = Math.floor(Math.random() * 30) + 1; // 1 <= secret <= 30
    let tries = 0;
    let guess = 0;

    console.log("How about a number between 1 and 30. What are you thinking?");

    while (guess !== secret) {
        const text = await rl.question("Take a guess: ");
        guess = parseInt(text, 10);

        tries = tries + 1;

        if (guess < 1 || guess > 30) {
            console.log("That number is way out of range. Let's try again.");
        } else if (guess < secret) {
            console.log("Too low, give it another try.");
        } else if (guess > secret) {
            console.log("It's too high, try again.");
        } else {
            console.log("Wow, finally. You got it after", tries, "tries!");
        }
    }
} finally {
    rl.close();
}
```

---

# Practice Result

I successfully ran my edited JavaScript program in the Linux CLI.

The program picked a number between 1 and 30.

I tested several guesses and received feedback:

```text
Too low
Too high
Correct
```

The final correct number was 21, and the program counted 9 tries.

This confirmed that:

* the random range worked
* the input prompt worked
* the loop worked
* the conditions worked
* the tries counter worked
* the program stopped after the correct guess

---

# Python vs JavaScript Comparison

| Concept           | Python                   | JavaScript                       |
| ----------------- | ------------------------ | -------------------------------- |
| File extension    | `.py`                    | `.js` or `.mjs`                  |
| Run file          | `python3 file.py`        | `node file.js` / `node file.mjs` |
| Print output      | `print()`                | `console.log()`                  |
| Variable          | `guess = 0`              | `let guess = 0;`                 |
| Constant          | no required keyword      | `const secret = 10;`             |
| User input        | `input()`                | `await rl.question()`            |
| Convert to number | `int(text)`              | `parseInt(text, 10)`             |
| If                | `if guess < secret:`     | `if (guess < secret) {`          |
| Else if           | `elif`                   | `else if`                        |
| Else              | `else:`                  | `else {`                         |
| OR                | `or`                     | `\|\|`                           |
| Not equal         | `!=`                     | `!==`                            |
| Equality check    | `==`                     | `===`                            |
| Loop              | `while guess != secret:` | `while (guess !== secret) {`     |
| Code block        | indentation              | `{ }`                            |

---

# Extended Learning

## Understanding vs Memorizing

I learned that I do not need to memorize every JavaScript function or syntax immediately.

The more important goal is to:

* understand what each part does
* recognize patterns
* practice small edits
* run the program
* read errors
* fix mistakes

Even experienced programmers use documentation and search for syntax when needed.

---

## JavaScript for Cybersecurity

JavaScript is important in cybersecurity because it powers much of the web.

Understanding JavaScript helps with:

* web applications
* browser behavior
* forms
* client-side validation
* cookies and tokens
* web requests
* XSS concepts
* frontend logic
* Node.js tools

Python is especially useful for automation and scripting, while JavaScript is especially useful for understanding web behavior.

---

# Key Takeaways

* JavaScript is used heavily in websites and web applications.
* Node.js allows JavaScript to run in the terminal.
* JavaScript files usually use `.js`, but `.mjs` is useful for module-style imports.
* `let` declares variables that can change.
* `const` declares values that should stay fixed.
* `console.log()` prints output.
* `Math.random()` creates a random decimal.
* `Math.floor()` rounds down.
* `parseInt(text, 10)` converts text into a number.
* `await rl.question()` asks for input and waits for the answer.
* `if`, `else if`, and `else` allow decision-making.
* `||` means OR in JavaScript.
* `!==` means not equal.
* `while` repeats code while a condition is true.
* Curly braces `{ }` define JavaScript code blocks.
* The program must update `guess` inside the loop so the loop can eventually stop.
* I practiced editing and running JavaScript from the Linux CLI.
* I successfully modified the guessing game from 1–20 to 1–30.

---

# Commands Used

```bash
mkdir JavaScript-Demo
cd JavaScript-Demo
nano guess_v3.mjs
node guess_v3.mjs
ls
cd ..
cat guess_v3.mjs
```

---

# Summary

Today I completed the **JavaScript: Simple Demo** room.

I learned how JavaScript handles variables, constants, input, output, conditionals, and loops.

I compared JavaScript with Python and saw that the programming logic is mostly the same, even though the syntax is different.

I also practiced using Linux CLI to create, edit, save, and run a JavaScript file with Node.js.

This was useful because it moved me from only reading code to actually editing and testing code myself.
