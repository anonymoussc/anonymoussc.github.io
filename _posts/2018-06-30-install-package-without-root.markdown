---
title:  "Install Package Without Root Privilege Bash Example"
date:   2018-06-30 11:00:00
summary: Install Package Without Root Privilege Bash Example
---

``` bash
which npm
```

``` bash
ls -ld /usr/local/bin/npm
```

``` bash
sudo chown -R $USER /usr/local/bin/npm
chmod -R o+rwx  /usr/local/bin/npm
```


---
> Quality is not an act, it is a habit.
> <small>- [Aristotle](https://www.brainyquote.com/quotes/aristotle_379604)</small>