---
title:  "Virtual machine : basic command"
date:   2017-12-31 12:40:00
categories: Software-Engineering
summary: VM Part 6 basic command.
---

### ls - List Directory Contents

```bash
# List contents of current working directory
ls

# List contents in a list form, with extra information:
ls -l

# List contents, including "hidden" files/folders
ls -la

# Add human-readable file/folder sizes:
ls -lah
```

### cd - Change Directory

```bash
# Change into the "/home/user/sites/sfh" directory.
cd /home/user/sites/sfh

# Same as above, but with the "~" shortcut
# to the current users home directory
cd ~/sites/sfh
```

### mkdir - Create a directory

```bash
# Create the `sfh` directory
# inside of /home/user/sites/sfh
mkdir ~/sites/sfh

# Create the /home/user/sites/sfh directory and
# any directory in between that doesn't exist
mkdir -p ~/sites/sfh
```

### rm - Delete a file or directory

```bash
# Delete (permanently) the `file.ext` file.
rm /path/to/file.ext

# Delete (recursively) the `/path/to/directory` directory.
rm -r /path/to/directory

# the additional `f` flag is to "force" the action,
# without prompting to make sure you want to do it.
# This is dangerous.
rm -rf /path/to/directory
```


---
> Law is vulnerable to the winds of intellectual or moral fashion, which it then validates as the commands of our most basic concept.
> <small>- [Robert Bork](https://www.brainyquote.com/quotes/robert_bork_110696)</small>