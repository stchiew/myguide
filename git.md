---
title: Git
nav_order: 2
layout: home
---

# Getting started
```
git clone https://github.com/stchiew/myguide.git
```
…or create a new repository on the command line
```
echo "# myguide" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/stchiew/myguide.git
git push -u origin master
```
…or push an existing repository from the command line
```
git remote add origin https://github.com/stchiew/myguide.git
git push -u origin master
```

### Overwrite local files from remote

If you feel the need to discard all your local changes and just reset/overwrite everything with a copy from the remote branch then you should follow this guide.

Important: If you have any local changes, they will be lost. With or without --hard option, any local commits that haven’t been pushed will be lost.
If you have any files that are not tracked by Git (e.g. uploaded user content), these files will not be affected.

The Overwrite workflow:
To overwrite your local files do:

```
git fetch --all
git reset --hard <remote>/<branch_name>
```

For example:

```
git fetch --all
git reset --hard origin/master
```

Ref: https://www.freecodecamp.org/forum/t/git-pull-how-to-override-local-files-with-git-pull/13216

### How to Clone a Specific Branch

You can

- Clone the repository and fetch only a single branch.

```
git clone -b <branchname> --single-branch <remote-repo-url> (e.g. git@github.com:stchiew/react-is-fun.git)
```

### Branches

Next, look at the local branches in your repository:
```
$ git branch
* master
```
But there are other branches hiding in your repository! You can see these using the -a flag:
```
$ git branch -a
* master
  remotes/origin/HEAD
  remotes/origin/master
  remotes/origin/v1.0-stable
  remotes/origin/experimental
```
Create a Git branch and checkout in one command:
```
$ git checkout -b <branch_name>
```
If you just want to take a quick peek at an upstream branch, you can check it out directly:
```
$ git checkout origin/experimental
```
But if you want to work on that branch, you'll need to create a local tracking branch which is done automatically by:
```
$ git checkout experimental
```
and you will see
```
Branch experimental set up to track remote branch experimental from origin.
Switched to a new branch 'experimental'
```
That last line throws some people: "New branch" - huh? What it really means is that the branch is taken from the index and created locally for you. The previous line is actually more informative as it tells you that the branch is being set up to track the remote branch, which usually means the origin/branch_name branch

Now, if you look at your local branches, this is what you'll see:
```
$ git branch
* experimental
  master
```