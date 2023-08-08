# Git reset

`!!` don't reset pushed commits, use revert instead

Git reset can be used to undo commits.

There is three type:

- `git reset --soft HEAD~`
- `git reset HEAD~`
- `git reset --hard HEAD~`

## --soft

Undo the commit, but keeps the changes in the staging area.

1. Move the HEAD to the given commit
2. Keeps the changes in the staging area
3. Keeps the changes in the working directory

## reset

Undo the commit, unstage the changes (can be added back with git add)

1. Move the HEAD to the given commit
2. Remove the changes from the staging area
3. Keeps the changes in the working directory

## --hard

`!!` destructive, it reset everything as it was in the given commit

Undo the commit, unstage the changes, reset the working directory

1. Move the HEAD to the given commit
2. Remove the changes from the staging area
3. Remove the changes from the working directory

## Squashing commit with git reset

Git reset can be used to combined several commit.

Let says we have this git history, and want to squash the last two commits:

```bash
* 044e0d0 (HEAD -> main) Fix typo in file2
* 044e0d0 change file2
* bf2874a Change file1
* 2d649b5 First commit

git reset --soft HEAD~2         # reset to 'change file1' commit
git commit -m "change file2"    # recommit with the change on file2 + the typo fix


# new history
* 044e0d0 change file2
* bf2874a Change file1
* 2d649b5 First commit

```
