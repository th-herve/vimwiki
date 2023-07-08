# Copying a File from One Git Branch to Another

You can copy one file that exist in a branch to another one that does
not have it.

To add `myFile.txt` from `main` to `branch2`:

1. Go on the branch you want to add the new file to:
    > git checkout branch2
2. Copy the file:
    > git checkout main -- myFile.txt
3. You should still be on branch2 with the file available
3. Add and commit the change
