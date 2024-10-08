# Description
Know of little and big endian?

## Walkthrough
Connect to the host using netcat

![alt text](/Easy/Misc/images/endianness1.png)

We are greeted by a puzzle to solve to gain access to the flag. 

To solve this challenge, we need to convert the provided word, "ielso," into both little-endian and big-endian representations.

- Little Endian: The least significant byte (LSB) is stored first.
- Big Endian: The most significant byte (MSB) is stored first.

Convert the Word to ASCII Values: First, convert each character of the word "ielso" to its ASCII representation:
i = 105
e = 101
l = 108
s = 115
o = 111

Little Endian Representation: In little-endian, we write the ASCII values in reverse order:

For "ielso":
ASCII: 105 101 108 115 111
Little Endian: 111 115 108 101 105

In hexadecimal, this would be:
o = 0x6F
s = 0x73
l = 0x6C
e = 0x65
i = 0x69

So the little-endian representation is:
6F 73 6C 65 69

Big Endian Representation: In big-endian, you keep the ASCII values in the same order:
For "ielso":
ASCII: 105 101 108 115 111

In hexadecimal, this would be:
Big Endian representation:
69 65 6C 73 6F

We are prompted to input the Little-endian values first (No spaces)
Once correct, we are prompted to enter the Big-endian representation.

![alt text](/Easy/Misc/images/endianness2.png)