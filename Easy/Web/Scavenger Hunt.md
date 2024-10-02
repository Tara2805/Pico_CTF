# Description
There is some interesting information hidden around this site. Can you find it?

## Walkthrough
First go to the site and open the inspect tool. 
We get the first part of the flag in a comment

![alt text](/Easy/Web/images/SH1.png)

Lets look at the other page contents. There is something in the .css file... Part 2 of the flag!

![alt text](/Easy/Web/images/SH2.png)

Ok so we found part 2 in the .css file, lets have a look at the .js file.

![alt text](/Easy/Web/images/SH3.png)

While, no flag.. it does give us a clue about where we should look next. 

*The /robots.txt file is a standard used by websites to provide instructions to web crawlers (also known as robots or spiders) about which pages or sections of the website should not be crawled or indexed. It helps manage the interaction between a site and web search engines like Google, Bing, etc.*

So we navigate to /robots.txt. The next piece of the flag is waiting for us!

![alt text](/Easy/Web/images/SH4.png)

Still not finished... but we have the next clue. 

*The .htaccess file is a configuration file used by the Apache web server to control website settings and behavior on a per-directory basis. It is placed in a specific directory (usually the root) and applies settings to that directory and its subdirectories. The name .htaccess starts with a dot, making it a hidden file in Unix-based systems.*

So we go to /.htaccess for the next part of the flag. 

![alt text](/Easy/Web/images/SH5.png)

Still NOT finished!! Theres another piece of the flag we need. The new clue suggests that the next part might be related to a Mac and storage, which could point toward something involving files commonly associated with macOS.

*.DS_Store is a metadata file that macOS creates in directories to store folder settings. Sometimes, these files are unintentionally left exposed on web servers.*

So we follow the trail and go to /.DS-Store. 

![alt text](/Easy/Web/images/SH6.png)

Yay! That took a while but we have pieced together the entire flag.