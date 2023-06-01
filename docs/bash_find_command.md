# Find

Find directory or files.

>`!! "+" replace an asterisk in the examples (vimwiki does not display them)`
 
find a dir:  
>find -name [dirName] -type d  
 
find a file:  
>find -path '++/[fileName]/++.py' -type f

finds file modified 1 day age:  
>find -mtime -1 

Can then execute cmd on found files:  
>find -name +.py -exec rm {} \;
