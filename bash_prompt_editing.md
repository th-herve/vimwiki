# Edit bash prompt

## Basics

| keybind        | action                        |
|----------------|-------------------------------|
| C-b / C-f      | Move cursor backward/forward  |
| C-d            | Delete char under cursor      |
| C-_            | Undo                          |
| C-u            | delete line                   |
| C-a C-e        | Move start/end of the line    |
| M-f / M-b      | Move forward/backward a word  |

> note: M = Alt

## Killing command

Killing refer to delete the text, but save it for later use. So past it back later.

| keybind | action                                |
|---------|---------------------------------------|
| C-k     | Kill from the cursor to end of line   |
| M-d     | Kill from cursor to end of word       |
| M-DEL   | Kill from cursor to beginning of word |
| C-y     | Past the last killed text             |

> Note: There is a way to repeat action with the Meta key, but I was to lazy to add it

## Searching command history

| keybind   | action                                                   |
|-----------|----------------------------------------------------------|
| C-r       | Open search his                                          |
| C-o       | Run the found command                                    |
| C-g       | Close command history                                    |
| C-p / C-n | Previous/next executed command (like the arrows up/down) |

> Note: Can also use `history` cmd

## Chaining commands

### Execute several command one after the other

You can execute several command in one prompt.  
Separate the cmd with `;` 
Or with `&&` if you don't want the next cmd to be executed if the previous one fails.

### Execute next cmd with output of previous

Command can be chain and pass the output of the previous as argument to the next.  
Separate command with `|` 

```bash
ls | grep .html
```

By itself, the pipe take the output of the previous command as `one` argument.  
To break the output into several arg, use `xargs`. 

```bash
ls | xargs echo
```
