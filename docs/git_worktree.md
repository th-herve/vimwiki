# Git worktree

Git worktree is used to checkout and work multiple git branches.

## Usage

Create a new work tree on another branch (run at the root of the project):

`git worktree add ../my-project-2 other-branch`

This will create a new directory `../my-project-2` on the other-branch, while keeping the current directory git status as it was.
Both directories link to the same git instance while keeping the branch state separation.

Remove it with: `git remove ../my-project-2`
