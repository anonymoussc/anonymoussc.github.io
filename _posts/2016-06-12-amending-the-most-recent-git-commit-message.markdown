---
title:  "Amending the most recent git commit message."
date:   2016-06-12 22:15:00
summary: http://stackoverflow.com/questions/179123/edit-an-incorrect-commit-message-in-git.
---

### Amending the most recent git commit message.

{% highlight Bash %}

# Will open your editor, allowing to change the commit message of the most recent commit.
git commit --amend

{% endhighlight %}

### Amending the most recent git commit message (direct).

{% highlight Bash %}

git commit --amend -m "New commit message"

{% endhighlight %}

### Changing the message of a commit that already being pushed to a remote branch.

{% highlight Bash %}

git push <remote> <branch> --force
# Or
git push <remote> <branch> -f

{% endhighlight %}

### Use interactive rebase.

{% highlight Bash %}

# N is the number of commits to the last commit you want to be able to edit
git rebase -i HEAD~N

{% endhighlight %}

### Reference :

1. [Edit an incorrect commit message in Git](http://stackoverflow.com/questions/179123/edit-an-incorrect-commit-message-in-git)

2. [git-commit(1) Manual Page](https://www.kernel.org/pub/software/scm/git/docs/git-commit.html)
