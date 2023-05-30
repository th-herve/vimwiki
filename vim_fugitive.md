# Vim fugitive

Git integration in nvim  
:help fugitive for documentation

## Basics

Run :Git or :G followed by a git command

|----------|---------------------|
| keybind  | action              |
|----------|---------------------|
| :G log   | Open log in a split |
| :G diff  |                     |
| :G add . |                     |


## Resolve merge conflict

See the difference between merging branches:
    :Gvdiffsplit
    left pane = current change 
    midde = merge conflict
    right pane = branch merging with 

|-----------|--------------------------------------|
| keybind   | action                               |
|-----------|--------------------------------------|
| [c / ]c   | Previous/next conflict               |
| d2o / d3o | Take change from the left/right pane |

