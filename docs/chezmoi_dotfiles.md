# Chezmoi dotfiles

Manage dotfiles cross platform with chezmoi.

To get started, see the [install and quick start](https://www.chezmoi.io/install/)

Get a full list of command with `chezmoi help`

## Manage dotfiles with chezmoi

1. Track a dotfile
> chezmoi add ~/.fileName

2. Edit a dotfiles
> chezmoi edit ~/.fileName
The edit does not take effect yet.

If you edit the file without `chezmoi edit`, you can still add it with either:
>`chezmoi add $file` or `chezmoi re-add`
or
> `chezmoi merge $file`

3. See difference
> chezmoi diff

4. Apply the changes
> chezmoi -v apply

5. Commit the changes
> chezmoi cd
> git add .
> git commit -m "my commit"
> git push
> exit

The exit at the end is used because chezmoi cd open a new shell.

The files are in: /home/user/.local/share/chezmoi

## Using chezmoi on multiple machine

On any machine where chezmoi is installed and init, you can pull and apply the latest changes from your repo with:
>chezmoi update -v

### Init on a new machine

[full installation](installation.md)

Once installed, you can set up a new machine with one line:
> chezmoi init --apply $GITHUB_USERNAME

>Note: if your repo is not named dotfiles, use the full repo link

or you can use this version if there is element you want to change before applying the dotefiles to a new machine:

1. Initialise it with you dotfiles repo
> chezmoi init https://github.com/$GITHUB_USERNAME/dotfiles.git

2. Check the changes that would be made
> chezmoi diff

3. Change the files if you'r not happy with the changes
> chezmoi edit $FILE

or merge the file:
> chezmoi merge $FILE

4. Apply the change
> chezmoi apply -v

5. After that you can keep updating from a machine to another with 
>chezmoi update -v
