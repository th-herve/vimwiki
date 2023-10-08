# Git interactive rebase

`!!` Only rebase that have not been pushed and shared `!!`

Open a interactive pop up allowing to rewrite commit history. (`!!` the commits are shown from oldest to newest)

Specify which commits you want to edit.

```bash
# edit last 3 commit
git rebase -i HEAD~3

# edit commit from HEAD to 2b504bee (not included)
git rebase -i 2b504bee
```

## Operations

### Change commits order

Move the commits line to the new order, and save.

```bash
# from:
pick 1a2b3c4d commit_1 
pick 9i0j1k2l commit_3 
pick 3m4n5o6p commit_2 

# to:
pick 1a2b3c4d commit_1 
pick 3m4n5o6p commit_2 
pick 9i0j1k2l commit_3 
```
## Change commit message

Replace `pick` with `r` or `reword`, save and exit. Then a new window appear where you can edit the commit message.

```bash
pick 1a2b3c4d commit_1 
r 9i0j1k2l commmmmmit_3 
```
## Squash commit

Squashing commits allows to combine two or more commits into one.

1. Replase `pick` with `s` or `squash`, the commit(s) you want to combine with the precedent, then save and exit.
2. A new window open where you can edit the commit message in the first line, save and exit

`!!` commits are from oldest to newest in the list

```bash
# from:
pick 1a2b3c4d commit_1 
pick 3m4n5o6p commit_2 
s 9i0j1k2l commit_3 

# to:
pick 1a2b3c4d commit_1 
pick 3m4n5o6p commit_2_3 
```
