# Day 20 – Python: Simple Demo

## TryHackMe Room

Python: Simple Demo
Explore what a basic Python program looks like.

---

# Topics Covered

## Introduction to Python

Today I started a new room focused on Python basics.

Python is a high-level, general-purpose programming language. High-level means it hides many low-level computer details and is easier for humans to read and write. General-purpose means it can be used for many different tasks, including:

* automation
* web applications
* cybersecurity scripts
* data analysis
* machine learning
* file processing
* small tools and games

In this room, I explored a simple Python program called **Guess the Number**.

The goal of the program is:

* the computer picks a secret number between 1 and 20
* the user guesses the number
* the program gives hints
* the program keeps asking until the user guesses correctly
* the program counts how many attempts were made

---

# Guess the Number Program

The final program uses three major programming concepts:

* variables
* conditional statements
* loops

These are important foundations in imperative programming.

---

# Variables

## What I Learned

A variable is a named storage location for data.

In the program, variables were used to store important values:

```python
secret = random.randint(1, 20)
tries = 0
guess = 0
```

## Variable Meanings

```text
secret = the random number chosen by the computer
tries  = the number of attempts made by the user
guess  = the current guess entered by the user
```

The program starts with:

```python
tries = 0
```

because the user has not made any guesses yet.

The program also starts with:

```python
guess = 0
```

because the secret number is between 1 and 20, so 0 cannot be the correct answer. This makes it a safe starting value before the user enters a real guess.

---

# Importing Modules

The program uses:

```python
import random
```

This imports Python’s `random` module.

The `random` module gives Python extra tools for generating random values.

The program then uses:

```python
random.randint(1, 20)
```

This chooses a random integer between 1 and 20.

Both 1 and 20 are included.

---

# Output with print()

The program uses `print()` to display messages to the user.

Example:

```python
print("I'm thinking of a number between 1 and 20")
```

This prints a message in the terminal.

`print()` is used when the program needs to show information.

---

# User Input with input()

The program uses `input()` to ask the user for a guess.

Example:

```python
text = input("Take a guess: ")
```

Important point:

`input()` always returns text, also called a string.

So if the user types:

```text
10
```

Python stores it as:

```python
"10"
```

not as:

```python
10
```

This matters because `"10"` is text, while `10` is a number.

---

# Type Conversion with int()

To compare the user’s guess with the secret number, the guess must be converted from text to an integer.

The program uses:

```python
guess = int(text)
```

This converts the text input into a whole number.

Example:

```python
text = "10"
guess = int(text)
```

After conversion:

```python
guess = 10
```

Now Python can compare the guess with the secret number.

---

# Counting Attempts

The program counts each guess using:

```python
tries = tries + 1
```

This means:

```text
Take the current value of tries, add 1, and store the result back into tries.
```

Example:

```text
tries = 0
tries = tries + 1
tries = 1
```

Each time the user makes a guess, `tries` increases by 1.

---

# Conditional Statements

## What I Learned

Conditional statements allow a program to make decisions.

The program uses:

```python
if
elif
else
```

These allow Python to check different possible cases.

---

## Conditional Logic Used in the Game

```python
if guess < 1 or guess > 20:
    print("That number is out of range. Try again.")
elif guess < secret:
    print("Too low, try again.")
elif guess > secret:
    print("Too high, try again.")
else:
    print("You got it in", tries, "tries!")
```

This checks whether the user’s guess is:

* outside the allowed range
* too low
* too high
* correct

---

# Understanding if / elif / else

## if

```python
if guess < 1 or guess > 20:
```

This checks the first condition.

It asks:

```text
Is the guess less than 1 OR greater than 20?
```

If yes, the number is out of range.

---

## elif

```python
elif guess < secret:
```

`elif` means “else if.”

It checks another condition only if the previous condition was false.

This line checks whether the guess is too low.

---

## Another elif

```python
elif guess > secret:
```

This checks whether the guess is too high.

---

## else

```python
else:
```

`else` runs only if none of the previous conditions were true.

If the guess is:

* not out of range
* not too low
* not too high

then it must be correct.

So the program prints the success message.

---

# Comparison Operators

The program used several comparison operators.

```text
<   less than
>   greater than
!=  not equal to
=   assignment / storing a value
==  equality check
```

Important difference:

```python
guess = 10
```

means assign/store 10 in `guess`.

```python
guess == secret
```

means check whether `guess` is equal to `secret`.

---

# Logical Operator: or

The program uses:

```python
if guess < 1 or guess > 20:
```

The `or` operator means only one of the conditions needs to be true.

So the guess is out of range if:

```text
guess is less than 1
OR
guess is greater than 20
```

Examples of out-of-range guesses:

```text
0
-5
21
30
100
```

---

# Loops / Iteration

## What I Learned

A loop repeats a block of code.

The program uses a `while` loop:

```python
while guess != secret:
```

This means:

```text
While the guess is not equal to the secret number, keep repeating the code inside the loop.
```

The symbol `!=` means “not equal to.”

---

# Why the while Loop Is Needed

Without a loop, the user only gets one guess.

With a loop, the program keeps asking until the user guesses correctly.

The repeated steps are:

```text
Ask for a guess
Convert the guess to a number
Add 1 to tries
Check the guess
Give feedback
Repeat if still incorrect
```

---

# How the Loop Stops

The loop continues while this condition is true:

```python
guess != secret
```

When the user finally guesses correctly, then:

```python
guess == secret
```

At that point:

```python
guess != secret
```

becomes false.

So the loop stops.

---

# Final Program

```python
import random  # gives us tools for picking random numbers

# ----------------------------
# Guess the Number (Beginner Demo)
# ----------------------------
# The computer picks a secret number.
# The player keeps guessing until they find it.

secret = random.randint(1, 20)  # a <= secret <= b
tries = 0
guess = 0  # start with a value that cannot be the secret (since secret is 1..20)

print("I'm thinking of a number between 1 and 20")

# Repeat until the user guesses the secret number.
while guess != secret:
    text = input("Take a guess: ")  # input() returns text (a string)
    guess = int(text)  # convert the text to a number
    
    tries = tries + 1  # add 1 try

    # Give a hint using if / elif / else.
    if guess < 1 or guess > 20:
        print("That number is out of range. Try again.")
    elif guess < secret:
        print("Too low, try again.")
    elif guess > secret:
        print("Too high, try again.")
    else:
        print("You got it in", tries, "tries!")
```

---

# Program Flow

The program works like this:

```text
1. Import the random module.
2. Pick a secret number between 1 and 20.
3. Set tries to 0.
4. Set guess to 0.
5. Print the starting message.
6. Start the while loop.
7. Ask the user for a guess.
8. Convert the input from text to integer.
9. Add 1 to tries.
10. Check if the guess is out of range.
11. Check if the guess is too low.
12. Check if the guess is too high.
13. If none of those are true, the guess is correct.
14. Stop when guess equals secret.
```

---

# Extended Learning

## Imperative Programming

This room introduced basic imperative programming.

Imperative programming means writing instructions step by step and telling the computer exactly what to do.

Example:

```text
Create a variable
Ask for input
Check a condition
Repeat a block of code
Print a result
```

The Guess the Number game is a simple example of imperative programming.

---

## Program State

I learned that variables represent the current state of the program.

For example:

```python
secret = 10
guess = 5
tries = 1
```

This tells us the current state of the game:

```text
The secret number is 10.
The user guessed 5.
The user has tried once.
```

When the user guesses again, the program state changes.

---

## Strings vs Integers

I learned the difference between strings and integers.

```python
"10"
```

is a string.

```python
10
```

is an integer.

Even though they look similar to a human, Python treats them differently.

This is why the program uses:

```python
guess = int(text)
```

to convert the user’s input into a number.

---

## Code Blocks and Indentation

Python uses indentation to show which lines belong together.

Example:

```python
while guess != secret:
    text = input("Take a guess: ")
    guess = int(text)
```

The indented lines belong inside the `while` loop.

In Python, indentation is required. It is not just for appearance.

This is different from some languages that use curly braces `{}` to define code blocks.

---

## Infinite Loops

I learned that a loop can run forever if the condition never becomes false.

Example problem:

```python
while guess != secret:
    print("Keep guessing")
```

If `guess` never changes, the loop may never stop.

In the game, the loop can stop because this line updates the guess:

```python
guess = int(text)
```

---

## Why guess Starts at 0

The variable `guess` starts at 0 because the secret number is between 1 and 20.

Since 0 cannot be correct, the first loop condition is guaranteed to be true.

```python
guess = 0
while guess != secret:
```

This starts the loop safely.

---

## Why else Works for the Correct Guess

The final `else` does not need to say:

```python
else guess == secret:
```

That is not valid Python.

Instead, `else` means all earlier conditions were false.

If the guess is:

* not out of range
* not too low
* not too high

then it must be correct.

---

# Practice Completed

I practiced running and reviewing the Python code in the TryHackMe VM.

I tested the program versions from the room and followed how the code changed from one version to the next:

```text
guess_v1.py
guess_v2.py
guess_v3.py
guess_v4.py
```

I practiced reading the program step by step and understanding how each part works.

I also practiced the final version of the Guess the Number game and observed how:

* the program picked a random number
* the program accepted user input
* the program converted the input to an integer
* the program counted attempts
* the program gave feedback using conditionals
* the program repeated using a while loop
* the program stopped when the correct number was guessed

---

# Cybersecurity Connection

Python is very useful in cybersecurity because it can automate repetitive tasks.

The same logic from this simple game can be used in real security scripts.

A cybersecurity script might:

* read log files
* check failed login attempts
* scan a list of IP addresses
* count suspicious events
* compare values
* repeat checks until finished
* print important results

The Guess the Number game uses the same basic pattern:

```text
store data
take input
convert data
compare values
make decisions
repeat until a condition is met
```

These are important skills for future cybersecurity scripting.

---

# Key Takeaways

* Python is a high-level, general-purpose programming language.
* Variables store information.
* `print()` displays output.
* `input()` gets user input as text.
* `int()` converts text into an integer.
* Conditional statements allow programs to make decisions.
* `if`, `elif`, and `else` control which code runs.
* A `while` loop repeats code while a condition is true.
* `!=` means not equal to.
* Indentation matters in Python.
* The Guess the Number game is simple, but it teaches real programming logic.
* Understanding code is the first step before being able to write it from scratch.
* Practice is required to become comfortable with programming.

---

# Commands / Files Used

```bash
python guess_v1.py
python guess_v2.py
python guess_v3.py
python guess_v4.py
```

Directory used in the TryHackMe VM:

```bash
/home/ubuntu/Python-Demo
```

---

# Summary

Today I completed the **Python: Simple Demo** room.

I learned how a basic Python program is structured and how variables, conditionals, and loops work together.

The main project was a simple Guess the Number game, but the concepts are much bigger than the game itself. These same ideas are used in real cybersecurity tools, automation scripts, and log analysis programs.

This was my first step into Python programming for cybersecurity.
