<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

# Table of Contents

- [Why Git?](#why-git)
  - [Preamble](#preamble)
  - [The purpose of git](#the-purpose-of-git)
- [Git Setup](#git-setup)
  - [Windows](#windows)
  - [OSX](#osx)
  - [Linux](#linux)
- [The Git Workflow](#the-git-workflow)
- [Essential Git Commands](#essential-git-commands)
  - [Creating a git repository (git init)](#creating-a-git-repository-git-init)
  - [Adding/Staging and Committing Changes](#addingstaging-and-committing-changes)
  - [Creating, Changing and Deleting Branches](#creating-changing-and-deleting-branches)
  - [Cloning a repository](#cloning-a-repository)
  - [Pushing Changes to a repository](#pushing-changes-to-a-repository)
  - [Pulling Changes from a repository](#pulling-changes-from-a-repository)
  - [Viewing History/Logs](#viewing-historylogs)
- [Resources](#resources)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Why Git?

## Preamble

Have you ever tried working on a project, with others before and ended up with a similar issue like this where you'd have different versions of the same file in the same folder?

```
final_project_v1.java

final_proj_slightly_broken.java

final_proj_fixed.java

final_proj_completed_v10.java

```

Now this is just a small example of the problem, but imagine working on a mid-large project, where you have to be working with different software versions.

It would actually be pretty easy to become really confused or to accidentally ship broken code off into production.

But this is where git shines.

## The purpose of git

So git is the most widely used version control system today, and its useful to anyone that writes codes or needs to keep track of changes to files.

So Git works by Git tracking the changes you make to files, so you have a record of what has been done, and you can revert to specific versions should you ever need to.

And the best part is, git also makes collaboration easier, allowing changes by multiple people to all be merged into one source.

# Git Setup

So git is widely available on most operating systems.
Use the following to set up git on your local machine based on your operating system.

## Windows

[Git for Windows](https://gitforwindows.org/)

## OSX

[Git for OSX](https://git-scm.com/download/mac)

## Linux

[Git for Linux](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

# Essential Git Commands

## Creating a git repository (git init)

A Git repository (or repo for short) contains all of the project files and the entire revision history.

To create a git repository on your local machine, navigate to an empty directory (or create one) and type `git init`:

This creates a hidden directory with the name `.git`

```bash
$ mkdir git-demo
$ git init
```

## Adding/Staging and Committing Changes

Think of Git as keeping a list of changes to files, and you'd want to tell git to record those changes. How could we accomplish that?

Well we can do that by making commits!

But, before we can make a commit we have to tell git the files you'd want to commit.

This is known as **staging** and is done with the `git add` command.

The syntax is as follows:

```bash
$ git add <filename>
$ git commit -m "Commit message"
```

or to add everything in your current directory

```bash
$ git add .
$ git commit -m "Commit message"
```

An example of this is done below

```bash
$ git add fancy_python.py
$ git commit -m "There's some fancy code here"
```

But wait, there's more!

If you'd like to add/stage and commit in one go, and you've already staged your file/s once, you can use the `-am` flag for `git commit` as seen below.

```bash
$ git commit -am "Added some more fancy code"
```

## Creating, Changing and Deleting Branches

Branches are used to develop features isolated from each other. The master/main branch is the "default" branch when you create a repository.

So git allows you branch out from your original code base, which alows you to easily work with other developers.

To create a branch the syntax is as follows:

```bash
$ git checkout -b <branch-name>
```

To switch between branches its also pretty simple!

```bash
$ git checkout <branch-name>
```

And to delete its just as simple

```bash
$ git branch -d <branch-name>
```

So here's a quick example switching, deleting and creating some branches

```bash
$ git checkout -b fancy_branch
$ git checkout master
$ git branch -d fancy_branch
```

## Cloning a repository

Now you may be wondering, how to get code that's already in a repository online?

Well that's where `git clone` comes into play

and its simply

```bash
$ git clone <repository-url>
```

An example is as follows

```bash
$ git clone https://github.com/Agezao/confetti-js.git
```

## Pushing Changes to a repository

After commiting your code, your changes will be in the HEAD of your local repository. So to push those changes to a remote repository on a platform like Github, you'll use the `git push`.

The syntax is as follows

```bash
$ git push <remote-name> <branch-name>
```

In the example below our remote is known as origin and our branch is the master branch

```bash
$ git push origin master
```

Now you aren't only limited to origin as your remote, as oftentimes you may end up working with multiple remotes, especially when collaborating with others.

So to add a new remote repository you will do

```bash
$ git remote add <remote-nickname> <repo-url>
```

Here's an example with one of my repositories

```bash
$ git remote add danga https://github.com/DangaRanga/git_practice.git
```

So in this case I have a new remote attached called `danga` and you can view your remote repositories by doing

```bash
$ git remote -v
```

## Pulling Changes from a repository

Aside from committing, staging and pushing, its essential to also know how to pull from a remote repository, and it's actually pretty simple

```bash
$ git pull <remote-name> <branch-name>
```

Example: Pulling from a remote with the name upstream

```bash
$ git pull upstream master
```

## Viewing History/Logs

To view a history of commits made to your git repository, the git you can use the `git log` command

```bash
$ git log
```

# Resources

- [Ultimate Git Guide](https://rogerdudler.github.io/git-guide/)
- [Why is git necessary?](https://www.nobledesktop.com/blog/what-is-git-and-why-should-you-use-it)
