# Description
Can you get the flag?

## Walkthrough
So we go to the website they have listed.

![alt text](/Easy/Web/images/la1.png)

We have an interface asking us for a username and password that needs to contain letters && numbers only!

So we immediately need to open up source code and have a peek

In index.html there is a section that is useful

![alt text](/Easy/Web/images/la2.png)

So we can go directly do these paths in the url
![alt text](/Easy/Web/images/la3.png)

Inspect the code again, there is a .js file assosiated with login.php that tells us a lot of hidden info

![alt text](/Easy/Web/images/la4.png)

Lets go back to the login interface and enter the details we have found and enter them.

The flag should be shown on the next screen

### Flag
picoCTF{XXXX}