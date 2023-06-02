# Git add only part of a file

When modifying a file in a project, you don't have to include every changes.
You can select what changes in a file to include or not with `Staging Patches`
This can be useful to exclude debugging print statement for example.

 
1. Use the `-p` flag along with add:
    > git add -p [file]

2. This will open an interactive prompt, for each section (or 'hunk') it will ask what you want to do.
    > press `?` for a list of possibility.

3. Press:
    1. `y`: to add the hunk
    2. `n`: to not add it
    3. `s`: to split it. For each element, you will be prompted for what you want to do
 
4. To see the changes staged:
    > git diff --cached

[more info](https://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging)
