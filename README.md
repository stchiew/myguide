# My Guide

Getting started
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

First, clone a remote Git repository and cd into it:
```
$ git clone git://example.com/myproject
$ cd myproject
```
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
