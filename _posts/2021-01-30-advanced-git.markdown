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

![image of app](https://dpenciso.github.io/blog/images/not-rebase.png)

## Git Reset, Checkout, and Revert

# What is git reset?

Git reset is a pretty strong command to use. Essentially, it undoes the local changes of the state of the repo. There are different kinds of reset that you can do and they are listed below:

### Hard

By adding <code>--HARD</code> to the end of <code>git reset</code> you are reseting the working directory, the staged snapshot of your code, and the commit history.

### Mixed

By adding <code>--MIXED</code> to the end of <code>git reset</code> you are reseting the staged snapshot of your code and the commit history.

### Soft

By adding <code>--SOFT</code> to the end of <code>git reset</code> you are just changing the commit history.

# What is git checkout?

Git checkout is a command that allows you to navigate between branches. In addition, if you write the command <code>git checkout -b "name"</code> you can create and navigate to a new branch at the same time.

# What is git revert?

Git revert is nice because instead of simply undoing, deleting, and orphaning commits, it makes a new commit that changes the code to a previous commits. This makes it easier to track the history of that code.

# In what ways are these commands the same and what ways are they different?

Git revert and git reset are similare in that they both change the state of your code. The difference is that revert does it in a way that you can still track the history of your code. Reset, on the other hand, erases that history and orphans those commits which will eventually be cleaned out and lost forever.

# When would you use reset, checkout, or revert?

You would use <code>reset</code> when you realize you have made some bad commits that you would like to undo and no longer keep track of. You could use <code>checkout</code> when you would like to branch off of your current code and make a new branch that you can make new changes on but also keep the original on the main branch. you would use <code>revert</code> when you would like to undo changes you make to the commit history, but track that history at the same time.

# Examples:

### Git reset

Hard

![image of app](https://dpenciso.github.io/blog/images/reset-hard.png)

Mixed

![image of app](https://dpenciso.github.io/blog/images/reset-mixed.png)

Soft

![image of app](https://dpenciso.github.io/blog/images/reset-soft.png)

### Git checkout

![image of app](https://dpenciso.github.io/blog/images/checkout.png)

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