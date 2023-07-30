# Bash command

## Basics commands

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

## Advanced commands

| key              | action                                                                                |
|------------------|---------------------------------------------------------------------------------------|
| cd-              | got back previous dir                                                                 |
| pushd dir / popd | mark the current dir and cd into the given one, use popd to go back to the marked dir |
| <C-z> / fg       | minimize a program and open a terminal, use fg to go back to the prog                 |
| !!               | repeat the last command (can be changed, for example sudo !!)                         |
| history          | open cmd history                                                                      |
| !<number>        | run the xth cmd from history                                                          |
| tail -f filenale | similar to `cat` but update in real time (usefull for log)                            |


### random cmd

| command                       | action                                                                   |
|-------------------------------|--------------------------------------------------------------------------|
| sort                          | sort input                                                               |
| uniq                          | remove duplicate in a sorted output                                      |
| uniq -c                       | uniq with count of each iteration                                        |
| tail                          | only print xth lines                                                     |
| awk                           | parse output by colone delimited by white space                          |
| paste                         | print the input in a given format (ex: on one line, seperated by a coma) |
| bc                            | calculator                                                               |
| lp <file>                     | print the file (printer must be configure)                               |
| scanimage -f pdf > output.pdf | scan image from printer at the given format                              |


## Other


| key                | action          |
|--------------------|-----------------|
| shellcheck file.sh | debug a script  |
| man cmd            | open cmd manual |

[cheat sheat](https://files.fosswire.com/2007/08/fwunixref.pdf)
