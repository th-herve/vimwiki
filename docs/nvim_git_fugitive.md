# Vim fugitive

Git integration in nvim  
:help fugitive for documentation

## Basics

Run :Git or :G followed by a git command

| keybind  | action              |
|----------|---------------------|
| :G log   | Open log in a split |
| :G diff  |                     |
| :G add . |                     |

## Custom keybind

| keybind (normal mod) | action                      |
|----------------------|-----------------------------|
| ld gs                | status                      |
| ld gaw               | add current file            |
| ld ga.               | add all                     |
| ld gcm               | commit with msg             |
| ld gc                | commit buffer               |
| ld gp                | push                        |
| ld gd                | see diff for merge conflict |
| ld gd                | see diff for merge conflict |

## Resolve merge conflict

See the difference between merging branches:
    :Gvdiffsplit (or :Gvdiff!, try several times if not working)
    left pane = current branch (main)
    midde = merge conflict
    right pane = branch merging with 

| keybind                 | action                               |
|-------------------------|--------------------------------------|
| [c / ]c                 | Previous/next conflict               |
| d2o / d3o               | Take change from the left/right pane |
| :diffget (autocomplete) | Take change from the left/right pane |

>Note: the left pane has /2/ in his name and /3/ for the right
> Usefull to know for the autocomplete
