---
title: "My Git Useful Commands"
date: 2020-06-26T01:11:15+05:30
draft: false
---
# My useful git commands

Useful git commands

## Table of contents

- [How to see my last commit](#how-to-see-my-last-commit)
- [How to output git log with the first line only?](#how-to-output-git-log-with-the-first-line-only)
- [How can i view a git log of just one user](#how-can-i-view-a-git-log-of-just-one-user)
- [How do I force git pull to overwire local files](#how-do-i-force-git-pull-to-overwire-local-files)
- [How do I determine the url of git repository](#how-do-i-determine-the-url-of-git-repository)
- [How do I go to specific revision](#how-do-i-go-to-specific-revision)
- [How do I tag a specific commit](#how-do-i-tag-a-specific-commit)
- [How do I delete a specific branch](#how-do-i-delete-a-specific-branch)
- [How to change author in a commit](#how-to-change-author-in-a-commit)
- [How to rename the git branch](#how-to-rename-the-git-branch)
- [How do I branch a specific commit](#how-do-i-branch-a-specific-commit)
- [How to reset the git password in windows](#how-to-reset-the-git-password-in-windows)
- [How to reset a git branch](#how-to-reset-a-git-branch)
- [How to reset a local commit](#how-to-reset-a-git-branch)
- [How to resolve merge conflicts](#how-to-resolve-merge-conflicts)
- [How to view git stash files](#how-to-view-git-stash-files)
- [How to git stash specific files under a path](#Git-stash-specific-files-under-a-path)
- [How to revert merge commit](#how-to-revert-merge-commit)
- [How to move a commit from one branch to another using cherry-pick](#how-to-move-a-commit-from-one-branch-to-another-using-cherry-pick)


## How to see my last commit

This command is useful to see 'my last commit'

```md
git log --name-status HEAD^..HEAD
```

## How to output git log with the first line only

This command is useful to print commit history by one line

```md
git log --pretty=oneline --abbrev-commit
```
