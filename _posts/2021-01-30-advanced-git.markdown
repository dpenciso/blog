---
layout: post
title: "Advanced Git"
date: 2021-01-29 14:02:00 -0600
categories: homework
---

## Git Rebase

# What is git rebase?

As mentioned in a previous post, Git is used for version control. In essence, it is a journal for you code. With Git you can choose to write code starting from a certain part in it's history and create what is called a branch. You can then merge your branch into the original code. Rebasing is the process of combining those commits to a new base commit. Instead of having a branch off of where you branched off, when rebased, the code of the branch ond original code now have the same base.

# What are some advantages and disadvantages of git rebase?


### Advantages:

- Git rebase makes the history of your code linear.
- Makes debugging easier since there is a clean history.

### Disadvantages:

- Git rebase can change the history of commits and make it harder to see the true past versions of files
- Git rebase makes it more difficult to solve conflicts since they must all be solved individually.

# When shouldn't you use git rebase?

You should not use git rebase on commits that exist outside of the repository on which you are working. This would cause collaborators a lot grief if they are working on another commit, they would have to re-merge their work and re-pull.

# Examples:

### A rebase merge

![image of app](https://dpenciso.github.io/blog/images/rebase.png)

### An interactive rebase merge

![image of app](https://dpenciso.github.io/blog/images/rebase-i-1.png)

![image of app](https://dpenciso.github.io/blog/images/rebase-i-2.png)

![image of app](https://dpenciso.github.io/blog/images/rebase-i-3.png)

### When you shouldn't rebase with a remote repo

asdf

## Git Reset, Checkout, and Revert

# What is git reset?

asdf

### Hard

asdf

### Mixed

asdf

### Soft

adsf

# What is git checkout?

asdf

# What is git revert?

asdf

# In what ways are these commands the same and what ways are they different?

asdf

# When would you use reset, checkout, or revert?

asdf

# Examples:

### Git reset

asdf

### Git checkout

#### Commit

asdf

#### File

asdf

### Git Revert

asdf

## Git Submodules

# What are git submodules?

asdf

# When would you use a submodule?

asdf

# What are the advantages and disadvantages of git submodules?

asdf