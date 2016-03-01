---
title:  "How to remove several commit from github and squash them into one through rebase"
date:   2016-02-29 18:02:00
summary: In Git there are two main ways to integrate changes from one branch into another, the merge and the rebase.
cover-image: chelovex-vyshka_1024.jpg
---

In Git there are two main ways to integrate changes from one branch into another the __merge__ and the __rebase__.

### "Undo" the last 3 push from remote repository

{% highlight Bash %}
# "Undo" (for example) the last 3 pushes from remote repository
git push -f origin HEAD^^^:master

# or also can use :

git push -f origin HEAD~3:master
{% endhighlight %}

In local repository the commit will be available as an un-pushes commit.

### Rebasing

Start the rebase :

{% highlight Bash %}
git rebase -i HEAD~3
{% endhighlight %}

After that an GNU nano (Ubuntu) editor will be opened. Example view of rebase screen below.

{% highlight Bash %}

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
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
{% endhighlight %}

To squash the last 2 commits to the first one, change the file into :

{% highlight Bash %}

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
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
{% endhighlight %}

Save (CTRL + S) the file and exit. Git may be asked to change the commit message, simply delete the last two and keep the one that will be pick.
Push the change into remote repository.


---
> Squash is my passion, and it is in my blood.
> <small>- [Jahangir Khan](http://www.brainyquote.com/quotes/quotes/j/jahangirkh688618.html)</small>