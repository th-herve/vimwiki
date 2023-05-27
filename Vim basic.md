
# === Vim basics  ===

# Enter the differents modes

|-------------------------|-----------------------------------|
| key                     | action                            |
|-------------------------|-----------------------------------|
| `i` `a`                 | insert mode                       |
| `shift + i` `shift + a` | insert mode beginning/end of line |
| `o` `O`                 | insert mode new line below/above  |
| `v`                     | visual mode                       |
| `shift + v`             | visual line mode                  |
| `:`                     | command mode                      |
| `esc`                   | normal mode                       |

# Normal mode

## Navigation

|-------------------------------|---------------------------------------------------------------------------------|
| key                           | action                                                                          |
|-------------------------------|---------------------------------------------------------------------------------|
| `h` `l`                       | cursor left/right                                                               |
| `j` `k`                       | cursor down/up                                                                  |
| `w` `b`                       | cursor next/previous word                                                       |
| `e`                           | cursor end word                                                                 |
| `gg` `shift + g`              | beginning/end file                                                              |
| `shift + %`                   | corresponding bracket                                                           |
| `f` `shift + f` + (character) | next/previous (character)                                                       |
| `t` `shift + t` + (character) | like above, but put you before the character                                    |
| `/` + (word)                  | enter to search the corresponding word, `n` `shift + n` next/previous occurence |
| `shift + h`                   | top of screen                                                                   |
| `shift + m`                   | middle of screen                                                                |
| `shift + l`                   | end of screen                                                                   |
| `0`                           | beginning of line                                                               |
| `$`                           | end of line                                                                     |
| `5gg` `5G`                    | go to line 5 (not just 5 ofc)                                                   |

## Scroll movement 

|--------------|------------------------------------|
| key          | action                             |
|--------------|------------------------------------|
| `ctrl + e y` | scrool down/up                     |
| `ctrl + f`   | scroll down 1 page                 |
| `ctrl + b`   | scroll up 1 page                   |
| `zz`         | scroll to put cursor in center     |
| `zt` `zb`    | scroll to put cursor beginning/end |


## Action

Copy/past

|-------------|------------------------------------|
| key         | action                             |
|-------------|------------------------------------|
| `y`         | copy                               |
| `yy`        | copy line                          |
| `2yy`       | copy 2 line or more                |
| `yw`        | copy word to beginning of next one |
| `yiw`       | copy word                          |
| `p`         | past                               |
| `P`         | past before cursor                 |
| `shift + p` | past on top of current line        |

Delete

|-------|------------------------------|
| key   | action                       |
|-------|------------------------------|
| `x`   | delete cursor char           |
| `dd`  | delete line                  |
| `wd`  | delete cursor to end of word |
| `diw` | delete word                  |
| `daw` | delte word + space           |
| `2dd` | delete 2 line or more        |
| `cc`  | delete line and type mode    |

>**Note:** everything deleted is added to the clipboard, see command for more deleting option

Other

|------------|----------------------------------------------------|
| key        | action                                             |
|------------|----------------------------------------------------|
| `r` + char | replace cursor char                                |
| `u`        | undo                                               |
| `ctrl + r` | redo                                               |
| `.`        | repeat last action                                 |
| `>>`       | indent line                                        |
| `<<`       | de indent line                                     |
| `>%`       | indent block in () or {} (cursor on brace)         |
| `<%`       | de indent block in () or {} (cursor on brace)      |
| `ctrl+w+v  | split window                                       |
| `~`        | in n mode, swap lowercase to upper and inversement |
| `gf`       | open file under cursor if exist                    |
|------------|----------------------------------------------------|

# Visual mode

|-------------|-------------------------|
| key         | action                  |
|-------------|-------------------------|
| `v`         | enter visual mode       |
| `shift + v` | enter visual line mode  |
| `ctrl + v`  | enter visual block mode |

Use navigation key to select text

|-------------|-------------------------------------------------------------|
| key         | action                                                      |
|-------------|-------------------------------------------------------------|
| `(shift) >` | indent selection                                            |
| `(shift) <` | de indent selection                                         |
| `ib`        | selection text in current parenthesis (shift b for bracket) |
| `ab`        | selection text and parenthesis (shift b for bracket)        |
| `u` `U`     | selection to lower/upper case                               |

# Commands

|--------------------------|--------------------------------------------|
| key                      | action                                     |
|--------------------------|--------------------------------------------|
| `:`                      | enter command mode                         |
| `q`                      | close file                                 |
| `w`                      | save file                                  |
| `wq`                     | close and save file                        |
| `terminal`               | open a terminal window (type exit to exit) |
| `!` command              | execute a terminal command                 |
| `ls`                     | list all the file open and their buffer    |
| `buffer`+ number         | switch to the corresponding file           |
| `next` `previous`        | switch to next/previous file               |
| `set (no)number`         | add/remove line number                     |
| `set (no)relativenumber` | add relative line numnber                  |
| `set mouse=a`            | enable the mouse                           |
| `set mouse= `            | disable the mouse                          |
| `vsplit`                 | split verticaly                            |

Delete

|---------|-----------------------------------------------|
| key     | action                                        |
|---------|-----------------------------------------------|
| `3,5d`  | delete line 3 to 5                            |
| `.,$d`  | delete from current line to end of file       |
| `.,1d`  | delete from current line to beginning of file |
| `10,$d` | delete from line 10 to end of file            |


# put selection in bracket
- v           Enter visual mode and select the text
- s           Substitute the selection with new text
- [           Type the opening bracket
- Ctrl+r %    Insert the closing bracket (it is ctrl+r, then %)
- Esc         Exit insert mode

# Open several file

In the terminal it is possible to open several file with vim with the command:

- vim folderName1 folderName2...
- vim *

# Create a config file
Create a file that set the vim config each time it is open

In terminal:
```bash
vim ~/.vimrc
```
Edit the file that open with command that will be executed each opening of vim
ex:

- set number
- set relativenumber
- ...

# file tree navigation

https://vonheikemen.github.io/devlog/tools/using-netrw-vim-builtin-file-explorer/


# specific action

## type same ting on severals lines

- enter visual block mode (ctrl+v, alt+v on my setup)
- select the lines to type on with jk
- press shift i (I)
- type the text (it will only display on 1 line firts)
- press esc and it should appear on all line


# vim spellcheck

- activate: set spell spelllang=en
- navigate to mispelled words with [s and ]s
- z= for word suggestion 
- zg to add word to dictionary zw to remove
- set nospell
