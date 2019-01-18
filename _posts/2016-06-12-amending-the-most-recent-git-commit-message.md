---
title:  "Amending the most recent git commit message."
date:   2016-06-12 22:15:00
summary: http://stackoverflow.com/questions/179123/edit-an-incorrect-commit-message-in-git.
---

### Amending the most recent git commit message.

```bash
# Will open your editor, allowing to change the commit message of the most recent commit.
git commit --amend
```

### Amending the most recent git commit message (direct).

```bash
git commit --amend -m "New commit message"
```

### Changing the message of a commit that already being pushed to a remote branch.

```bash
git push <remote> <branch> --force

# Or

git push <remote> <branch> -f
```

### Use interactive rebase.

```bash
# N is the number of commits to the last commit you want to be able to edit
git rebase -i HEAD~N
```

### Reference :

1. [Edit an incorrect commit message in Git](http://stackoverflow.com/questions/179123/edit-an-incorrect-commit-message-in-git)

2. [git-commit(1) Manual Page](https://www.kernel.org/pub/software/scm/git/docs/git-commit.html)
