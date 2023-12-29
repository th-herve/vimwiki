# Arch aur

## Install package

Make sure the base-devel package is installed.
Set up a directory where to clone all aur repo.

1. Find package on the aur site
2. Grab the git url
3. Git clone the url
4. Cd into the cloned repo
5. Check for malicous stuff and all
6. Run `makepkg` as normal user
7. Run `sudo pacman -U packagename.pkg.tar.zst` (the name of the file can be found in the cloned repo)

## Update package

Aur package must be updated manually.
If pacman updates dependencies for aur pkg, it needs to be rebuild

1. Run `git pull` in the cloned repo
2. Run `makepkg` as normal user
3. Run `sudo pacman -U packagename.pkg.tar.zst` (the name of the file can be found in the cloned repo)
