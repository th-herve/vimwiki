# === Git command ===

## Branches

| command                               | description                                             |
|---------------------------------------|---------------------------------------------------------|
| git branch                            | list the branches                                       |
| git branch (name)                     | Create a new branch with the given name                 |
| git checkout (branch-name)            | Switch to the given branch                              |
| git checkout -b (branch-name)         | Create and switch to a new branch                       |
| git checkout -                        | Switch to the last branch checkedout                    |
| git diff (branch-name) (other-branch) | Display the differences between two branches or commits |

## Repository

### Basics

| command                 | description                                                     |
|-------------------------|-----------------------------------------------------------------|
| git init                | Initialize a new Git repository in the current directory        |
| git clone (url)         | Copy the given repo                                             |
| git pull                | Retrieve and merge the remote changes                           |
| git add (filename)      | Stage changes made to a file for commit                         |
| git commit              | Commit changes (will open an editor for the message)            |
| git commit -m 'message' | Commit changes with a message describing the changes            |
| git status              | Display the current status of the working directory             |
| git push                | Push changes from the local repository to the remote repository |

## Advanced

| command                         | description                                                                |
|---------------------------------|----------------------------------------------------------------------------|
| git reset --hard (commit)       | Reset the current branch to the specified commit                           |
| git reset --hard origin/master  | Reset the current branch to the version on the remote repository           |
| git merge (branch to merge)     | Merge the specified branch with the current branch                         |
| git commit --amend              | Change the message of the last commit (better not do it if already pushed) |
| git commit --amend -m "message" | Change the message of the last commit (better not do it if already pushed) |
| git checkout (commit number)    | Switch to the specified commit                                             |

## Log

| command                              | description                           |
|--------------------------------------|---------------------------------------|
| git log                              | Log of the current branch             |
| git log --oneline                    | Log of the current branch in one line |
| git log --graph --oneline --decorate | Better looking log                    |
| git shortlog                         | Shorter log                           |


## Add aliases

Example, create an alias to use ac instead of commit -am
> git config --global alias.ac "commit -am"

```bash
git ac "commit message"
```
