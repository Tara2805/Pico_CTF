# Description
I accidentally wrote the flag down. Good thing I deleted it!
You download the challenge files here:
challenge.zip

## Walkthrough
Download and extract the files. Inspecting the extracted files shows us that the flag was removed during a previous git commit. 
Navigate to the directory and we can see a message.txt file. We want to check the File Metadata- To view details about the message.txt file:
    stat message.txt

![alt text](/Easy/Misc/images/CI1.png)

Now we need to view the Commit History, so we can see the previous commits in the repository:
    git log

![alt text](/Easy/Misc/images/CI2.png)

So now we have the hash values of the commits. So now we can view changes in a Specific Commit: To see the changes made in the most recent commit or any specific commit:
    git show <commit-hash>

![alt text](/Easy/Misc/images/CI3.png)

Got the flag!