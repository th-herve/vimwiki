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
