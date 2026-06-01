# Day 19 — Data Encoding

## TryHackMe Room

Data Encoding

---

# Topics Covered

## Introduction to Data Encoding

Today I completed the TryHackMe room **Data Encoding**.

In the previous room, I learned how computers represent numbers and colors using bits. In this room, I learned how computers represent text, symbols, different languages, and emojis.

The main idea is:

```text
Computers store everything as bits and numbers.
Characters are also represented as numbers.
Encoding tells the computer which number means which character.
```

For example, the computer does not directly store the letter `A` as a visual letter. It stores a number that represents `A`.

---

# Representation vs Encoding

## Representation

Representation means that data exists inside the computer as bits and numbers.

Example:

```text
01000001
```

This is just binary data.

## Encoding

Encoding is the agreed rule or mapping that gives meaning to those numbers.

Example:

```text
01000001 = 65 = A
```

So the encoding tells the computer:

```text
This number means this character.
```

Without the correct encoding, the same bytes can be displayed incorrectly.

---

# Characters Are Numbers

A character is a visible text symbol, such as:

```text
A
b
5
@
!
ت
Ω
😊
```

The computer stores these characters as numbers.

Example:

```text
A = 65 in ASCII
```

So when the computer reads the number `65` using ASCII, it displays:

```text
A
```

This helped me understand that text files are not really storing “letters” visually. They are storing bytes that get interpreted as characters.

---

# Number vs Character

One important distinction I learned is the difference between a number and a character.

## Number

```text
5
```

This is a numeric value.

It can be used for math:

```text
5 + 5 = 10
```

## Character

```text
"5"
```

This is a text symbol.

It looks like the number five, but it is stored as a character.

In ASCII:

```text
"5" = decimal 53
```

So:

```text
Number 5      = numeric value
Character "5" = text symbol
```

They look similar to humans, but the computer treats them differently depending on context.

---

# ASCII

ASCII stands for:

```text
American Standard Code for Information Interchange
```

ASCII is an early character encoding standard.

It maps numbers to English letters, digits, punctuation, and control characters.

Original ASCII uses 7 bits.

```text
7 bits = 2^7 = 128 combinations
```

So ASCII can represent values from:

```text
0 to 127
```

Important:

```text
0-127 does not mean 127 bits.
```

It means:

```text
7 bits can create 128 different combinations.
```

---

# Useful ASCII Examples

I do not need to memorize the whole ASCII table, but some useful anchors are:

```text
Space = 32
@     = 64
A     = 65
B     = 66
C     = 67
a     = 97
b     = 98
c     = 99
0     = 48
5     = 53
```

The useful pattern is that letters and digits are in order.

If:

```text
A = 65
```

then:

```text
B = 66
C = 67
```

If:

```text
a = 97
```

then:

```text
b = 98
c = 99
```

---

# ASCII Example: Character A

The uppercase letter `A` can be represented as:

```text
Decimal:      65
Hexadecimal:  41
Binary:       01000001
Character:    A
```

So:

```text
65 = 0x41 = 01000001 = A
```

This shows how one character can be represented in decimal, hexadecimal, and binary.

---

# ASCII Example: TryHackMe

If the text file contains:

```text
TryHackMe
```

the file stores the character codes, not actual visual letters.

In hexadecimal, it can be represented as:

```text
54 72 79 48 61 63 6b 4d 65 0a
```

Breakdown:

```text
54 = T
72 = r
79 = y
48 = H
61 = a
63 = c
6b = k
4d = M
65 = e
0a = new line
```

The `0a` represents a newline, similar to pressing Enter.

This also connects back to Day 18:

```text
4 bits = 1 hex digit
8 bits = 2 hex digits = 1 byte
```

So one ASCII character commonly fits into one byte.

---

# Why ASCII Was Limited

ASCII was mainly designed for English.

It can handle:

```text
English letters
digits
punctuation
basic control characters
```

But it cannot properly handle:

```text
Persian
Arabic
Chinese
Japanese
Greek
emojis
many European accented letters
symbols such as chess pieces
```

Examples of characters ASCII cannot fully cover:

```text
ñ
€
あ
龍
😊
♞
```

ASCII was useful, but it was too small for the whole world.

---

# Extended ASCII and Encoding Problems

Since ASCII used 7 bits, people tried using 8-bit encodings to add more characters.

8 bits gives:

```text
2^8 = 256 combinations
```

But 256 characters are still not enough for all languages.

Different regions created different encodings, such as:

```text
ISO-8859-1
ISO-8859-2
Windows-1252
```

The problem is that the same byte could mean different characters in different encodings.

Example idea:

```text
Same number/byte
Different encoding table
Different displayed character
```

This is why a file saved with one encoding can appear as weird gibberish when opened with another encoding.

---

# Gibberish / Mojibake

Weird broken text can happen when bytes are decoded using the wrong encoding.

Correct process:

```text
Bytes → correct encoding → correct characters
```

Wrong process:

```text
Bytes → wrong encoding → gibberish
```

Example:

```text
سلام
```

could appear incorrectly as something like:

```text
Ø³Ù„Ø§Ù…
```

The bytes may not be destroyed. They may simply be interpreted using the wrong encoding table.

This is similar to using the wrong dictionary to translate a message.

---

# Unicode

Unicode was created to solve the problem of many different incompatible encodings.

Unicode is a universal character standard.

It assigns a unique number to characters from many languages and symbol systems.

That unique number is called a:

```text
Code point
```

Unicode allows computers to represent:

```text
world languages
symbols
emojis
chess pieces
math symbols
historic writing systems
```

---

# Unicode Code Points

A Unicode code point is written like this:

```text
U+0041
```

The `U+` means Unicode.

Examples:

```text
U+0041 = A
U+03A9 = Ω
U+3042 = あ
U+062A = ت
U+265E = ♞
U+1F60A = 😊
```

So Unicode gives every character an official number.

This avoids the problem of different regions creating different meanings for the same number.

---

# Character, Code Point, and Encoding

This was one of the most important ideas from the room.

## Character

The symbol we see:

```text
A
```

or:

```text
😊
```

## Code Point

The official Unicode number:

```text
A = U+0041
😊 = U+1F60A
```

## Encoding

The method used to store the code point as bytes:

```text
UTF-8
UTF-16
UTF-32
```

The process is:

```text
Character → Unicode code point → encoding → bytes
```

Example:

```text
😊 → U+1F60A → UTF-8/UTF-16/UTF-32 bytes → stored in file or memory
```

---

# Unicode vs UTF

Unicode and UTF are related, but they are not exactly the same thing.

## Unicode

Unicode is the universal list of characters and their code points.

## UTF-8, UTF-16, UTF-32

UTF encodings are ways to store Unicode code points as bytes.

Simple way to remember:

```text
Unicode = character number system
UTF = storage method
```

---

# UTF-8

UTF-8 is very common on the modern web.

It stores Unicode using:

```text
1 to 4 bytes per character
```

UTF-8 is efficient because it uses only as many bytes as needed.

Examples:

```text
ASCII characters like A = 1 byte
Some non-English characters = 2 or 3 bytes
Many emojis = 4 bytes
```

Important:

```text
UTF-8 is backward compatible with ASCII.
```

That means ASCII characters from 0 to 127 are stored the same way in UTF-8.

This is one reason UTF-8 became so common.

---

# UTF-16

UTF-16 stores Unicode using:

```text
2 or 4 bytes per character
```

Many common characters use 2 bytes.

Some emojis and rarer characters use 4 bytes.

Important:

```text
UTF-16 does not always mean 2 bytes per character.
```

Sometimes it needs two 16-bit units, which totals 4 bytes.

---

# UTF-32

UTF-32 stores every Unicode code point using:

```text
4 bytes
```

This makes it simple, but wasteful.

Example:

```text
A = 4 bytes
😊 = 4 bytes
🔥 = 4 bytes
```

The advantage is simplicity.

The disadvantage is that it uses more storage, especially for simple English text.

---

# UTF Comparison

```text
UTF-8:
1 to 4 bytes
Efficient
Most common on the web

UTF-16:
2 or 4 bytes
Used in some systems and programming environments

UTF-32:
Always 4 bytes
Simple but wasteful
```

---

# Emoji Encoding

Emojis are not stored as tiny pictures in normal text.

They are represented by Unicode code points.

Example:

```text
😊 = U+1F60A
```

The computer stores the encoded bytes.

Then the operating system, browser, app, or font displays the emoji image.

So the process is:

```text
Emoji character → Unicode code point → encoded bytes → font/display rendering
```

This helped me understand that emojis are also data, just like letters and numbers.

---

# Extended Learning

## Why Encoding Matters in Cybersecurity

Encoding matters in cybersecurity because text and byte interpretation appear in many areas:

```text
web pages
URLs
logs
email headers
phishing messages
malware strings
file analysis
packet analysis
terminals
payloads
input validation
```

If a program interprets bytes incorrectly, it may display broken text or process data in an unexpected way.

Understanding encoding also helps when looking at:

```text
hex dumps
file contents
network traffic
strings inside malware
web requests
```

---

# Extended Learning: Mental Model

The best way to visualize data encoding:

```text
Character:
A

Code point:
U+0041

Encoding:
UTF-8

Stored as:
bytes

Displayed as:
A
```

Another example:

```text
Character:
😊

Code point:
U+1F60A

Encoding:
UTF-8, UTF-16, or UTF-32

Stored as:
bytes

Displayed as:
emoji
```

The character is what humans see.

The code point is the official number.

The encoding is how the computer stores that number.

The bytes are what actually exist in memory or a file.

---

# Key Takeaways

```text
Computers store text as numbers and bytes.
```

```text
Encoding maps numbers to characters.
```

```text
ASCII is an older 7-bit encoding system.
```

```text
ASCII supports 128 characters.
```

```text
ASCII is mainly useful for basic English text.
```

```text
Extended ASCII tried to add more characters but created compatibility problems.
```

```text
Unicode gives characters from many languages a universal code point.
```

```text
UTF-8, UTF-16, and UTF-32 are ways to store Unicode code points as bytes.
```

```text
UTF-8 is the most common on the modern web.
```

```text
Gibberish text usually happens when bytes are decoded using the wrong encoding.
```

```text
Characters, symbols, chess pieces, and emojis are all represented by code points and stored as bytes.
```

---

# Personal Understanding

The biggest thing I learned today is that text is not stored as visual letters. Text is stored as numbers, and encoding gives meaning to those numbers.

I also understood that ASCII was like a small dictionary for English characters, while Unicode is like a huge universal dictionary for world languages, symbols, and emojis.

The most important connection I made was:

```text
Day 18:
Bits represent numbers and colors.

Day 19:
Bits also represent characters, symbols, and emojis.
```

So now the bigger picture is clearer:

```text
Bits → numbers → characters/colors/symbols/emojis
```

Everything still comes back to binary.

---

# Practice Examples

## ASCII Example

```text
A
```

ASCII:

```text
Decimal: 65
Hex: 41
Binary: 01000001
```

## Character vs Number

```text
5
```

as a number means:

```text
numeric value 5
```

But:

```text
"5"
```

as a character means:

```text
text symbol 5
```

In ASCII:

```text
"5" = decimal 53
```

## Unicode Example

```text
ت
```

Unicode:

```text
U+062A
```

## Emoji Example

```text
😊
```

Unicode:

```text
U+1F60A
```

---

# Summary

Today I learned how computers encode text. ASCII maps basic English characters to numbers, but it is limited. Unicode solves this by assigning universal code points to characters from many languages, symbols, and emojis. UTF-8, UTF-16, and UTF-32 are different ways to store those Unicode code points as bytes. I also learned why text can appear as gibberish when it is opened using the wrong encoding.
