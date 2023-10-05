# Windows shell

| cmd       | linux    | example   |
|-----------|----------|-----------|
| dir       | ls       |           |
| cd        | cd       |           |
| cd \      | cd ~     |           |
| mkdir     | mkdir    |           |
| copy      | cp       |           |
| del       | rm       |           |
| echo      | echo     |           |
| type      | cat      |           |
| *         | wildcard | del *.txt |
| echo %cd% | pwd      |           |
| ren       |          | rename    |

To go to a given drive: `d:` c: e: ...

> redirect
echo test > test.txt

>> concat
echo test >> test.txt

## Create env variable

```cmd
set MSG=Hello
echo %MSG%
```

### Script

`.bat` or `.cmd` file

Usually start with `@echo off`

Comment by beginning a line with `rem`

`pause` to ask to type a word
`pause > nul` to remove the message

#### Variable

```cmd
set myvariable=Text to display
rem for a int
set /a mynumber=1

echo %myvariable%
```
To prompt, use the /p flag

```cmd
set /p option=enter an option
```
#### Argument

Use %1, %2...

```cmd
echo %1
```
#### Operator

if ()
else ()
NOT
EXIST: dos a file exist
EQU: ==
LSS: <
GTR: >
NEQ: !=
LEQ: <=
GEQ: >=

```cmd
set p=apple
if not [%1] equ [%p%] (
  echo no apple
) else (
  echo apple
)
```

### Pointer

use `GOTO` and `:` to jump around code

```cmd
@echo off
goto myligne

echo ligne1
echo ligne2
:myligne
echo ligne3
```

Can be use to create a loop

```cmd
:start
echo It's %time%
goto start
```

#### Loop

Use the `for` keyword with %%i and `do` where %%i is the loop variable. (can be any one letter %%a %%b...)

```cmd
@echo off

set city=Paris,New York, London
for %%i in (%city%) do (
    echo %%i
)
```

##### for /f

Execute a command for each line. The line can be break down into tokens.

```cmd
for /f "tokens=1,2 delims=," %%a in (data.cvs) do (
  echo First token: %%a
  echo Second token: %%b
)
```

## Command

| cmd      | description                  | example             |
|----------|------------------------------|---------------------|
| tree     | print the tree of the dir    |                     |
| prompt   | change prompt                | prompt type:        |
| compact  | compress and decompress file | compact test.txt    |
| variable | display system version       |                     |
| find     | find line in a text          | find hello test.txt |
