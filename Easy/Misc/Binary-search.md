# Description
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.
Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!
You can download the challenge files here:
challenge.zip

## Walkthrough
This is all about reducing the amount of data to search for. Instead of going through 1 through to 1000 we use the script output to determine our next input. So if we enter 500 and the cli tells us "lower" we can do 250 etc.

My attempt:

![alt text](/Easy/Misc/images/bs1.png)

Once we get the result, we get the flag :)

### Flag
Seen in image