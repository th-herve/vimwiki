# === Git and git hub ===

# participate on git hub

1. Clone the repo
    * On git hub, forked the repo, click code and copy the url (https or ssh)
    * In terminal: go to the directory you want to clone in, cmd:
    ```bash
     git clone url
     ```
2. Create branch
    * branch naming convention: category/reference/description-in-kebab-case
    * ex: bugfix/issue#1903/fixe-typo-in-main-file
    ```bash
    git switch -c <new-branch-name>
    ```
3. make change in the files
4. add the files to track
    ```bash
    git add <files>
    or
    git add .
    ```
5. Commit the change
    ```bash 
    git commit -m "describe changes"
    ```
6. Push
    ```bash
    git push -u origin <your-branch name>
    ```
7. Submit
    * on git hub, click compare and pull request

8. To modify the pull request if needed, repeat step 3, 4, 5, 6

See more [here](https://github.com/firstcontributions/first-contributions)

