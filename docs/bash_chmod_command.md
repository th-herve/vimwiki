# chmod

Change permission of a file or directory.  

> chmod [user][operator][permission] [file/dir name]

| user    | operator | permission       |
|---------|----------|------------------|
| u,g,o,a | +, -, =  | r, w, x, X, s, t |


```bash
chmod +x file
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
chmod 777 file
chmod 734 file
chmod 440 file
```
