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

| keybind (normal mod) | action           |
|----------------------|------------------|
| gs                   | status           |
| gaw                  | add current file |
| ga.                  | add all          |
| gcm                  | commit with msg  |
| gc                   | commit buffer    |

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
