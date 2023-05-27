# === Bash command ===

## == Basics commands ==

|----------------------------------|------------------------------|
| key                              | action                       |
|----------------------------------|------------------------------|
| `cd` folderName                  | change directory             |
| `cd` ..                          | go back in directory         |
| `mkdir`                          | make a directory             |
| `ls`                             | list directory content       |
| `cat` fileName                   | show content of file in bash |
| `pwd`                            | show current directory path  |
| `mv` filename directoryName      | moove a file                 |
| `cp` copiedFile newFile          | create a copy of a file      |
| `rm` fileName                    | remove file                  |
| `rm` -d directory                | remove empty directory       |
| `rm` -r directory                | remove directory recursivly  |
| `rm` * .txt                      | remove every txt files       |
| `find` . -name file.txt          | file.txt in this folder      |
| `find` . -name "*.txt"           | search all txt file          |
| `find` . -type d -name directory | search for a directory       |
|----------------------------------|------------------------------|

## == Advanced commands ==

|------------------|---------------------------------------------------------------------------------------|
| key              | action                                                                                |
|------------------|---------------------------------------------------------------------------------------|
| cd-              | got back previous dir                                                                 |
| pushd dir / popd | mark the current dir and cd into the given one, use popd to go back to the marked dir |
| <C-z> / fg       | minimize a program and open a terminal, use fg to go back to the prog                 |
| !!               | repeat the last command (can be changed, for example sudo !!)                         |
| history          | open cmd history                                                                      |
| !<number>        | run the xth cmd from history                                                          |
| tail -f filenale | similar to `cat` but update in real time (usefull for log)                            |


### chmod

Change permission of a file or directory.  

> chmod [user][operator][permission] [file/dir name]

| user    | operator | permission       |
|---------|----------|------------------|
| u,g,o,a | +, -, =  | r, w, x, X, s, t |


```bash
chmod a+r file
chmod o-w file
chmod ug=rx file
chmod u= file
```
An other way is to use 3 digit to specify the permission, in this order, of the user, group and others.  

| Number | Binary | Resulting Permission |
|--------|--------|----------------------|
| 0      | 000    | ---                  |
| 1      | 001    | --x                  |
| 2      | 010    | -w-                  |
| 3      | 011    | -wx                  |
| 4      | 100    | r--                  |
| 5      | 101    | r-x                  |
| 6      | 110    | rw-                  |
| 7      | 111    | rwx                  |

```bash
chmod 734 file
chmod 440 file
```

### Find

find a dir:  
>find -name test -type d  
 
find a file:  
>find -path '++/test/++.py' -type f

finds file modified 1 day age:  
>find -mtime -1 

Can then execute cmd on found files:  
>find -name +.py -exec rm {} \;

>`!! "+" replace an asterisk (vimwiki does not display them)`

### Sed

used for performing operations on text files, such as searching, replacing, inserting, deleting, and transforming text based on specified patterns or commands.

### wc

Count the number of line, word, character in a file or input.  
> wc [option] [file]

- -l : lines
- -w : words
- -c : bytes or character

### du/df

Give the disk usage.  
> Get a list of all the element in the location: `du -sh *` 
> Get usage of all file system with `df -h`

### random cmd

|-------------------------------|--------------------------------------------------------------------------|
| command                       | action                                                                   |
|-------------------------------|--------------------------------------------------------------------------|
| sort                          | sort input                                                               |
| uniq                          | only print once lines in a sorted input (remove duplicate)               |
| uniq -c                       | uniq with count of each iteration                                        |
| tail                          | only print xth lines                                                     |
| awk                           | parse output by colone delimited by white space                          |
| paste                         | print the input in a given format (ex: on one line, seperated by a coma) |
| bc                            | calculator                                                               |
| lp <file>                     | print the file (printer must be configure)                               |
| scanimage -f pdf > output.pdf | scan image from printer at the given format                              |


## == Other ==


|--------------------|-----------------|
| key                | action          |
|--------------------|-----------------|
| shellcheck file.sh | debug a script  |
| man cmd            | open cmd manual |

[cheat sheat](https://files.fosswire.com/2007/08/fwunixref.pdf)
