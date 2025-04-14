# Git add file to past commit

## To add to the last commit

```bash
git add myfile.txt
git commit --amend --no-edit
```

## To add to any commit

Use `interactive rebase`:

1. If you have untracked file, stash them (including the file to add)
```bash
git stash
```
2. Start rebasing to the commit you want to add the file 

```bash
git rebase -i [commithash]^
```

3. In the file that opens, find the commit you want to add the file to and change `pick` to `edit`. Then close the file.
4. Add the file to the commit. If it has been stash, pop it first.

```bash
# pop the stash if the file is not untracked
git stash pop

# add the file
git add myfile.txt

# if other files were in the stash, stash them again
git stash

# amend the commit
git commit --amend --no-edit

```
5. Continue the rebase

```bash
git rebase --continue
```
