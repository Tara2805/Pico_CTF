# Description
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.
You can download the challenge files here:
challenge.zip

## Walkthrough
Download the file and launch the instance. 

Connect via SSH
    ssh -p xxxxx ctf-player@rhea.picoctf.net

We have been given the password so enter it to connect. 
Once in, run ls to see what we have.

![alt text](/Easy/Crypto/images/verify1.png)

Now we want to verify the checksum of the files and calculate the SHA-256 checksum of the files to find the legitimate one.

To find the checksum we need to:
    sha256sum path/to/file

We need to repeat until we find the file that has a matching sum to the one we were supplied.
Once we've identified the correct file with the matching checksum, use the provided decryption script to decrypt it.

I tried to use grep to find the matching file to no avail (because it's encrypted!)
    grep -r "3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4" /home/ctf-player/drop-in/files

If we open /files we can see theres a ton of files and when clicked they all contain a checksum.
Lets use the file command to see if theres anything different
    file *

Sure enough 1 file sticks out!

![alt text](/Easy/Crypto/images/verify2.png)

So this is the file we need to use the decrypt.sh on
    ./decrypt.sh files/e018b574 

### Flag: 
picoCTF{xxxxxx}