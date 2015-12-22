---
title:  "Symbolic link definition and example"
date:   2015-09-09 22:45:09
categories: Software-Engineering Symlink
summary: In computing, a symbolic link (also symlink or soft link) is a special type of file that contains a reference to another file or directory.
---

> In computing, a symbolic link (also symlink or soft link) is a special type of file that contains a reference to another file or directory in the form of an absolute or relative path and that affects pathname resolution. 
> <small>- [Symbolic link](https://en.wikipedia.org/wiki/Symbolic_link)</small>

### Create symlink

Syntax :

    ln -s /path/ linkname

Example (symlinking php executable):

    ln -s /opt/lampp/bin/php /usr/local/bin/php

### Remove symlink

Syntax :

    rm linkname


---
> By failing to prepare, you are preparing to fail. 
> <small>- [Benjamin Franklin](http://www.brainyquote.com/quotes/quotes/b/benjaminfr138217.html)</small>
