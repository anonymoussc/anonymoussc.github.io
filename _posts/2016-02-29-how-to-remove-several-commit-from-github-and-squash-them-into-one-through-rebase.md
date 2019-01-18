---
title:  "How to remove several commit from github and squash them into one through rebase"
date:   2016-02-29 18:02:00
summary: In Git there are two main ways to integrate changes from one branch into another, the merge and the rebase.
cover-image: chelovex-vyshka_1024.jpg
---

In Git there are two main ways to integrate changes from one branch into another the __merge__ and the __rebase__. For example, we will undo the last 3 push from remote.

### "Undo" the last 3 push from remote repository

```bash
# "Undo" (for example) the last 3 pushes from remote repository
git push -f origin HEAD^^^:master

# or also can use :

git push -f origin HEAD~3:master
```

The last 3 commit will be available in local.

### Rebasing

Start the rebase :

```bash
git rebase -i HEAD~3
```

After that an GNU nano (Ubuntu) editor will be opened. Example view of rebase screen below.

```bash
...
pick 5x7ef96 ok
pick b90dre9 ok
pick 738s56h ok

#
# Commands:
#  p, pick = use commit
#  r, reword = use commit, but edit the commit message
#  e, edit = use commit, but stop for amending
#  s, squash = use commit, but meld into previous commit
#  f, fixup = like "squash", but discard this commit's log message
#  x, exec = run command (the rest of the line) using shell
#  d, drop = remove commit
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```

To squash the last 2 commits to the first one, change the file into :

```bash
...
pick 5x7ef96 ok
s b90dre9 ok
s 738s56h ok

#
# Commands:
#  p, pick = use commit
#  r, reword = use commit, but edit the commit message
#  e, edit = use commit, but stop for amending
#  s, squash = use commit, but meld into previous commit
#  f, fixup = like "squash", but discard this commit's log message
#  x, exec = run command (the rest of the line) using shell
#  d, drop = remove commit
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```

### GNU nano (Ubuntu).

Save _(CTRL + x)_ the file and exit, next question, then choose _yes / no_ (by pressing y or n) and push `enter` to confirm. Next Git will asked you to change the commit message, simply delete the last two and keep the one that will be pick (or do other possible task), and again; save _(CTRL + x)_ the file and exit, next question, choose _yes / no_ (by pressing y or n) and push `enter` to confirm.

Push the change into remote repository.

__Edit 2017/11/05-E01__

Notes (_fixup and __vim editor___) :
- Choose `f` or `fixup` = like "squash", but discard the commit's log message.
- vim editor: Type `i` to insert or start editing
- vim editor: To quit, type `esc` to enter "Command mode"
    - `:q` to quit (short for `:quit`)
    - `:q!` to quit without saving (short for `:quit!`)
    - `:wq` to write and quit
    - `:wq!` to write and quit even if file has only read permission (if file does not have write permission: force write)
    - `:x` to write and quit (similar to `:wq`, but only write if there are changes)
    - `:exit` to write and exit (same as `:x`)
    - `:qa` to quit all (short for `:quitall`)

### Edit 2017/11/05-E01: Add notes.
### Edit 2017/11/05-E01 24:04 AM: Further edit, more clarity about vim editor and stuff.


---
> Squash is my passion, and it is in my blood.
> <small>- [Jahangir Khan](https://www.brainyquote.com/quotes/quotes/j/jahangirkh688618.html)</small>