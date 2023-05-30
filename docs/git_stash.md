# Git stash

The `git stash` command can be use to save changes, without committing them.
Useful when switching branch, but having unfinished changes on another.

You can have as many stash entry as you want.

## Basic use

1. stash changes made to a branch, if you have untracked file (file `never checked`), include them with `-u`
    > git stash
    or
    > git stash -u

2. reapply those changes with
    > git stash pop

> Note: `pop` apply the last stash entry and delete it.

 
## Other related command

| command                   | action                                                                 |
|---------------------------|------------------------------------------------------------------------|
| git stash apply           | apply the last stash entry but does not delete it (as oppose to `pop`) |
| git stash list            | list all the available stash entry                                     |
| git stash apply stash@{n} | apply the nth stash (get the number with stash list)                   |
| git stash drop stash@{n}  | delete the nth stash                                                   |
| git stash clear           | clear all the stash                                                    |
