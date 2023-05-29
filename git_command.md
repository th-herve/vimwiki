# === Git command ===

| Command                               | Description                                                                |
|---------------------------------------|----------------------------------------------------------------------------|
| git branch                            | Display the current branch and a list of branches                          |
| git branch <name>                     | Create a new branch with the given name                                    |
| git checkout <branch-name>            | Switch to the specified branch                                             |
| git checkout <commit number>          | Switch to the specified commit                                             |
| git diff <branch-name> <other-branch> | Display the differences between two branches or commits                    |
| git pull                              | Fetch and merge changes from the remote repository to the local repository |
| git clone <url>                       | Create a copy of the repository on your local machine                      |
| git add <filename>                    | Stage changes made to a file for commit                                    |
| git commit -m 'message'               | Commit changes with a message describing the changes                       |
| git status                            | Display the current status of the working directory                        |
| git push                              | Push changes from the local repository to the remote repository            |
| git log                               | Display the history of commits in the current branch, press q to quit      |
| git log --oneline                     | Display the history of commits in the current branch, press q to quit      |
| git shortlog                          | Display the history of commits in the current branch, press q to quit      |
| git reset --hard <commit>             | Reset the current branch to the specified commit                           |
| git reset --hard origin/master        | Reset the current branch to the version on the remote repository           |
| git merge <branch to merge>           | Merge the specified branch with the current branch                         |
| git init                              | Initialize a new Git repository in the current directory                   |
| git commit --amend                    | Change the message of the last commit (better not do it if already pushed) |
