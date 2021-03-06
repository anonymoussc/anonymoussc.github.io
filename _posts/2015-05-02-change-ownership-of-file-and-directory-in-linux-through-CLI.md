---
title:  "Change ownership of file and directory in Linux through CLI"
date:   2015-05-02 07:39:40
categories: Software-Engineering CLI
summary: Change permission and ownership file and directory in ubuntu linux using terminal.
---

### Change user and group ownership of a file

Syntax command as follow :

    sudo chown user:group file.ext
    

### Change user only without a group ownership of a file 

Syntax command as follow :

    sudo chown user: file.ext
    
I.e we want to change package.json file owned by root to user anonymous.

    sudo chown anonymous package.json

### Change user and group ownership of a directory.

Syntax command as follow :

    sudo chown user:group directory
    
I.e we want to change package.json file owned by root and group by root to user anonymous and group by anonymous.
    
    sudo chown anonymous:anonymous package.json


### Change user and group ownership of a directory & sub-directory.

Syntax command as follow :

    sudo chown -R user:group directory

I.e we want to change directory owned by root and group by root into user anonymous and group by anonymous recursively to all of its sub-directory (including files).

    sudo chown -R anonymous:anonymous directory

The recursive switch `-R` used to make sure all child objects get the same ownership changes.

### Delete directory, subdirectory and file owned by root

Syntax command as follow :

    sudo rm -Rf directory_name

Example : 

    sudo rm -Rf node_modules
    
In the above example, the _node_modules_ directory, along with all files and directories within that directory, would be deleted with no prompt or message.

Explanation :

    sudo = root
    rm = remove
    -R = recurrsive
    -f = force

---
> To me, constructive criticism is when people take ownership of their ideas. That's why I don't listen to anything that's anonymous. But it's hard; when there's something hurtful out there, I still want to read it over and over and memorize it and explain my point of view to the person. 
> <small>- [Brene Brown](https://www.brainyquote.com/quotes/quotes/b/brenebrown553083.html)</small>
