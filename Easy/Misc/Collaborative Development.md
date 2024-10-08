# Description
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?
You can download the challenge files here:
challenge.zip

## Walkthrough
Download and extract the files, then cd into the drop-in directory. Lets run the .py file within

![alt text](/Easy/Misc/images/cd1.png)

Ok, so we need to perfrom some more analysis. Lets view file history. 
    stat flag.py

![alt text](/Easy/Misc/images/cd2.png)

Lets view the logs
    git log

![alt text](/Easy/Misc/images/cd3.png)

So theres possibly something within these previous versions...
Lets use git log on the commit hash
    git show <hash>

![alt text](/Easy/Misc/images/cd4.png)

Lets look at other git branches
    git branch -a

![alt text](/Easy/Misc/images/cd5.png)

Lets switch to each of the branches and have a look around
    git switch <branch-name>

By switching into part-1 branch and doing git log, we see a commit hash. Lets explore it more

![alt text](/Easy/Misc/images/cd6.png)

So it looks like we have a partial flag - we will need to go through the other branches and repeat the process to uncover the full flag.
    git switch <branch-name>
    git log
    git show <commit-hash>

Repeating this process and going through each branch gives us the full flag!