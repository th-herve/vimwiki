# g++ compiler

C++ is a compiled language. The C++ source code must be 
translated to machine code before it can be run.


## Basic use

```bash
g++ -o execName codName.cpp
```
Result in an executable file.

## Using several file

```bash
g++ file1.cpp file2.cpp -o main
```
Function from file2 used in file1 must have `forward declaration` in file1 or be included in a `header file`
>Note: `!!`do not add `#include file2.cpp` 

## Specify a header directory

If header files used are not in the same directory of the code file,
a directory to look for can be specify with `-I`. (it is not recursive, subdir wont be included if not specify)
Use it as many time as needed.

```bash
g++ -o main -I/source/headerDir1 -I/source/headerDir2
```


## Setting warnings

Setting high warning can be Usefull to learn and avoid mistake.  
Use -Wall, -Wextra, -Weffc++ and -Wsign-conversion

```bahs
g++ -Wall -Wextra -o hello hello.cpp
```

Additionally, the flag -Werror can be use to treat each warning as an error and stop the compilation.


## Setting language standard

Refer to the version of C++ to use.  
Use this flag: -std=c++11, -std=c++17 or -std=c++20 etc.
