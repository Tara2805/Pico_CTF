# Description
Can you get the real meaning from this file.

# Walkthrough
Download and open the file. We get the following:

YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6ZzVNR3N5TXpjNWZRPT0nCg==

Now this looks like a base64 encryption so lets use cyberchef.

When we input this and the cyberchef recipe we get:

![alt text](/Easy/Crypto/images/interencdec1.png)

This still looks base64 encoded. However, we need to remove the 'b'' to get the recipe to work. 

![alt text](/Easy/Crypto/images/interencdec2.png)

Now lets open up dcode.fr to read the type and decode it. So it's given us a few possibilities. After going through many of them I've worked it out to be the ceaser cipher. Now enter the previously decoded string into this site and get the flag. 