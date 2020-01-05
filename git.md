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
