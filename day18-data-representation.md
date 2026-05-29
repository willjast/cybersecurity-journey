# Day 18 — Data Representation

## TryHackMe Room

Data Representation

---

# Topics Covered

## Introduction to Data Representation

Today I started and completed the TryHackMe room **Data Representation**.

This room explained how computers represent numbers and colors using only two states:

```text
0 = off
1 = on
```

Computers do not naturally understand decimal numbers, colors, text, images, or videos the way humans do. At the lowest level, everything is represented using binary patterns made from 0s and 1s.

---

# Decimal System

## Base-10

Humans usually use the decimal system.

Decimal uses ten digits:

```text
0 1 2 3 4 5 6 7 8 9
```

Example:

```text
213
```

means:

```text
2 hundreds
1 ten
3 ones
```

or:

```text
213 = 2×100 + 1×10 + 3×1
```

In powers:

```text
213 = 2×10^2 + 1×10^1 + 3×10^0
```

The decimal system is called **base-10** because each place value is based on powers of 10.

---

# Binary System

## Base-2

Computers use binary because electronic systems work well with two clear states:

```text
0 = low/off
1 = high/on
```

Binary uses only two digits:

```text
0 1
```

Binary is called **base-2** because each place value is based on powers of 2.

---

# Binary Place Values

The most useful binary place values are:

```text
128 64 32 16 8 4 2 1
```

For 4-bit examples:

```text
8 4 2 1
```

Example:

```text
1001
```

Place values:

```text
8 4 2 1
1 0 0 1
```

Only the positions with `1` are counted:

```text
8 + 1 = 9
```

So:

```text
1001 = 9
```

---

# Bits

A **bit** means binary digit.

A bit can be:

```text
0
```

or:

```text
1
```

Example:

```text
1011
```

has 4 bits.

Example:

```text
11111111
```

has 8 bits.

---

# Bytes

A **byte** is 8 bits.

```text
1 byte = 8 bits
```

Example:

```text
11111111
```

is one byte.

Example:

```text
00000000
```

is also one byte.

A byte can create 256 different combinations because:

```text
2^8 = 256
```

The values are labeled from:

```text
0 to 255
```

Important:

```text
0-255 does not mean 255 bits.
```

It means:

```text
8 bits can create 256 different binary combinations.
```

The lowest 8-bit combination is:

```text
00000000 = 0
```

The highest 8-bit combination is:

```text
11111111 = 255
```

This is because:

```text
128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255
```

---

# Understanding Combinations

The key idea is that bits create combinations.

## 1 Bit

```text
0
1
```

Total:

```text
2 combinations
```

## 2 Bits

```text
00
01
10
11
```

Total:

```text
4 combinations
```

## 3 Bits

```text
000
001
010
011
100
101
110
111
```

Total:

```text
8 combinations
```

## 8 Bits

```text
2^8 = 256 combinations
```

This is why one byte can represent 256 possible values.

---

# Representing Colors

Computers represent colors using RGB.

RGB stands for:

```text
Red
Green
Blue
```

A color can be created by mixing different intensities of red, green, and blue light.

---

# First 8 Colors

If each color can only be on or off, then each color has 2 states:

```text
Red   = on or off
Green = on or off
Blue  = on or off
```

This gives:

```text
2 × 2 × 2 = 8 colors
```

The 3-bit format is:

```text
RGB
```

Examples:

```text
000 = Black
001 = Blue
010 = Green
100 = Red
011 = Cyan
101 = Magenta
110 = Yellow
111 = White
```

Example:

```text
100
```

means:

```text
Red   = on
Green = off
Blue  = off
```

So the color is red.

Example:

```text
111
```

means:

```text
Red   = on
Green = on
Blue  = on
```

So the color is white.

Example:

```text
000
```

means:

```text
Red   = off
Green = off
Blue  = off
```

So the color is black.

---

# Modern RGB Color

Modern computers do not limit each color to only on or off.

Instead, each RGB color channel gets one byte.

```text
Red   = 8 bits
Green = 8 bits
Blue  = 8 bits
```

Each channel can have values from:

```text
0 to 255
```

That means each channel has:

```text
256 possible intensity levels
```

So RGB color uses:

```text
3 bytes
```

or:

```text
24 bits
```

because:

```text
8 bits red + 8 bits green + 8 bits blue = 24 bits
```

---

# 16 Million Colors

Each RGB channel has 256 possible values.

```text
Red   = 256 possibilities
Green = 256 possibilities
Blue  = 256 possibilities
```

Total possible colors:

```text
256 × 256 × 256 = 16,777,216
```

So 24-bit RGB can represent over 16 million colors.

---

# RGB Example

Binary:

```text
11111111 00000000 00000000
```

Breakdown:

```text
Red   = 11111111 = 255
Green = 00000000 = 0
Blue  = 00000000 = 0
```

Meaning:

```text
Red   = maximum intensity
Green = no intensity
Blue  = no intensity
```

Result:

```text
Pure red
```

The first byte is fully on, while the green and blue bytes are fully off.

---

# Visual Understanding: Switches and Transistors

A useful way to picture binary is like switches.

```text
1 = switch on
0 = switch off
```

For one byte:

```text
11111111
```

all 8 switches are on.

For one byte:

```text
00000000
```

all 8 switches are off.

At the hardware level, computers use physical states such as voltage levels and transistor states. A transistor can represent a low or high state, which the computer interprets as 0 or 1.

For learning purposes:

```text
1 = on / high / active
0 = off / low / inactive
```

For RGB color, the binary values do not directly mean the exact LED is being powered by that written number. Instead, the computer stores the binary value, and the graphics hardware/monitor interprets that value as brightness intensity.

Example:

```text
Red = 255
```

means maximum red brightness.

```text
Green = 0
Blue = 0
```

means green and blue are off.

The monitor then displays the pixel as red.

---

# Hexadecimal System

## Base-16

Hexadecimal is a shorter way to write binary.

Hexadecimal uses 16 symbols:

```text
0 1 2 3 4 5 6 7 8 9 A B C D E F
```

The letters represent:

```text
A = 10
B = 11
C = 12
D = 13
E = 14
F = 15
```

---

# Binary to Hex

Every 4 bits can be represented as one hexadecimal digit.

```text
4 bits = 1 hex digit
```

Examples:

```text
0000 = 0
0001 = 1
0010 = 2
0011 = 3
1010 = A
1011 = B
1100 = C
1101 = D
1110 = E
1111 = F
```

Example:

```text
11111111
```

Split into groups of 4 bits:

```text
1111 1111
```

Convert each group:

```text
1111 = F
1111 = F
```

So:

```text
11111111 = FF
```

This is why:

```text
11111111 00000000 00000000
```

can be written as:

```text
FF0000
```

which represents pure red.

---

# Hex Color

A hex color usually uses 6 hexadecimal digits:

```text
RRGGBB
```

Example:

```text
#FF0000
```

Breakdown:

```text
FF = Red
00 = Green
00 = Blue
```

Meaning:

```text
Red   = 255
Green = 0
Blue  = 0
```

Result:

```text
Pure red
```

Other examples:

```text
#00FF00 = green
#0000FF = blue
#FFFFFF = white
#000000 = black
```

---

# Octal System

## Base-8

Octal uses 8 digits:

```text
0 1 2 3 4 5 6 7
```

Every 3 bits can be represented as one octal digit.

```text
3 bits = 1 octal digit
```

Examples:

```text
000 = 0
001 = 1
010 = 2
011 = 3
100 = 4
101 = 5
110 = 6
111 = 7
```

Octal is less common than hexadecimal, but it appears in Linux permissions.

Examples:

```text
755
644
777
```

---

# Why This Matters In Cybersecurity

Understanding binary and hexadecimal is important because they appear in many cybersecurity areas.

Examples:

## Network Traffic

Packet data in tools like Wireshark often appears in hexadecimal.

Example:

```text
45 00 00 54
```

## IP Addresses

IPv4 addresses use values from 0 to 255 in each section.

Example:

```text
192.168.1.1
```

Each section is one byte.

## File Signatures

Files can be identified by hex signatures.

Example:

```text
FF D8 FF
```

## Hashes

Hashes are often shown in hexadecimal.

Example:

```text
5f4dcc3b5aa765d61d8327deb882cf99
```

## Memory Addresses

Memory addresses are commonly shown in hexadecimal.

Example:

```text
0x7ffd1234
```

---

# Key Takeaways

```text
1 bit = 0 or 1
```

```text
8 bits = 1 byte
```

```text
1 byte = 256 possible combinations
```

```text
8 bits can represent values from 0 to 255
```

```text
Binary uses base-2
```

```text
Decimal uses base-10
```

```text
Hexadecimal uses base-16
```

```text
Octal uses base-8
```

```text
4 bits = 1 hex digit
```

```text
2 hex digits = 1 byte
```

```text
RGB uses 3 bytes
```

```text
24-bit RGB = over 16 million colors
```

---

# Personal Understanding

The biggest thing I learned today is that binary values are not random. They are combinations.

For example:

```text
11111111
```

is not just a random group of ones. It is the highest possible 8-bit combination.

It represents:

```text
255
```

because all the binary place values are turned on:

```text
128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255
```

For colors, I learned that RGB can be visualized as three rows of switches or three brightness sliders:

```text
Red
Green
Blue
```

Each one can go from 0 to 255.

So:

```text
11111111 00000000 00000000
```

means red is fully on, while green and blue are fully off.

That creates pure red.

This helped me understand how numbers, colors, transistors, binary combinations, and monitor colors connect together.

---

# Practice Examples

## Binary to Decimal

```text
1001
```

Place values:

```text
8 4 2 1
1 0 0 1
```

Add the active values:

```text
8 + 1 = 9
```

So:

```text
1001 = 9
```

---

## Binary to Hex

```text
10100011
```

Split into 4-bit groups:

```text
1010 0011
```

Convert:

```text
1010 = A
0011 = 3
```

So:

```text
10100011 = A3
```

---

## RGB Color

```text
11111111 00000000 00000000
```

Breakdown:

```text
Red   = 255
Green = 0
Blue  = 0
```

Result:

```text
Pure red
```

---

# Summary

Today I learned how computers represent numbers and colors using binary. I learned that bits create combinations, bytes store values from 0 to 255, RGB colors use three bytes, and hexadecimal makes binary easier to read. I also connected this to the physical idea of switches, transistors, and monitor pixels, which helped me understand why computers can represent colors and numbers using only 0s and 1s.
