---
title:  "Syncing a fork"
date:   2015-05-02 08:04:31
categories: Software-Engineering GitHub
summary: To sync changes in a fork with the original repository, developer must configure a remote that points to the upstream repository in Git.
---

### Configuring a remote for a fork

To sync changes in a fork with the original repository, developer must configure a remote that points to the upstream repository in Git.

1. List the current configured remote repository for your fork.

        git remote -v

2. Specify a new remote upstream repository that will be synced with the fork.

        git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git

3. Verify the new upstream repository you've specified for your fork.
    
        git remote -v    

### Syncing a fork

Sync a fork of a repository to keep it up-to-date with the upstream repository.

1. Change the current working directory to your local project.
2. Fetch the branches and their respective commits from the upstream repository. Commits to master will be stored in a local branch, upstream / master.

        git fetch upstream

3. Check out your fork's local master branch.

        git checkout master

4. Merge the changes from upstream/master into your local master branch. This brings your fork's master branch into sync with the upstream repository, without losing your local changes.

        git merge upstream/master

If your local branch didn't have any unique commits, Git will instead perform a "fast-forward".

### Pushing to a remote
1. Use 'git push  REMOTENAME BRANCHNAME' to push your local branch to a remote repository.

        git push origin master

### Reference :

1. [Configuring a remote for a fork](https://help.github.com/articles/configuring-a-remote-for-a-fork/ "Configuring a remote for a fork")
2. [Syncing a fork](https://help.github.com/articles/syncing-a-fork/ "Syncing a fork")
3. [Pushing to a remote](https://help.github.com/articles/pushing-to-a-remote/ "Pushing to a remote")


---
> Markets are frequently ahead of, and often out of sync with, the economy. 
> <small>- [Barry Ritholtz](http://www.brainyquote.com/quotes/quotes/b/barryritho692933.html)</small>
