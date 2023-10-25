# Git fix file too large to push

If you can't push because one or more files exeed the github limit of 100MB:

1. Locally delete the large files
2. Commit the deleted files
3. Soft reset to the commit where the large file where added: `git reset --soft HEAD~x`
4. Recommit all the changes
5. Push!

[source](https://stackoverflow.com/questions/19573031/cant-push-to-github-because-of-large-file-which-i-already-deleted)
