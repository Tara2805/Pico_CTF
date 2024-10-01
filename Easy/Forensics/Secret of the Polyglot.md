# Description
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?
Download the suspicious file here.

## Walkthrough
first simply open the file with ImageMagick to get the first part of the flag. We know with the lack of a closing brace this is not a complete flag.

![alt text](/Easy/Forensics/images/polyglot1.png)

Then look at the original .pdf content... it looks like the end of an opening tag.

![alt text](/Easy/Forensics/images/polyglot2.png)

Together they make the entire flag. 