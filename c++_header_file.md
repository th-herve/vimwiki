# C++ header file

Use to link files of a project together.  
Contain the `forward declaration` of a given code file.

[Header_file_example](Header_file_example)

The header file must have the same name of the corresponding code file.  
Example: add.cpp header is: add.h

## Create a header file

add

```cpp
int add(int x, int y);
```

## Include the header in a code file

```cpp
#include "add.h";
```
>Note: a header file is in between "" not < >

## Header can include other header

Header files often include other header files through the use of #include directives. 
These additional header files, known as `transitive includes,` are implicitly included when the first header file is included.  
However, it is best practice to explicitly include all the necessary header files in each code file.

## Header guards

All header file should include header guards.   
It ensures that the contents of the header are included only once in a same file during compilation, preventing duplicate definitions and allowing for proper compilation and linking.

Header guards are conditional compilation directive that take this form:

```cpp
#ifndef SOME_UNIQUE_NAME
#define SOME_UNIQUE_NAME

// declaration

#endif
```
If SOME_UNIQUE_NAME has already be define (ex: in another file that include the same header), it won't be included again.
>Note: `!!` be sure do give it a unique name, a generic name like CONFIG_H is to common and risk of giving the same name to two files is important.  
> Convention: <PROJECT><PATH or RANDOM_NUM or CREATION_DATE>H

>Note: some compiler support an alternative way with `#pragma once`. Included at the start of a header file, it has the same purpose(but can be less reliable)

## Header file #include order

If header files are written properly, the order should not matter.  
But it is best practice to order it in this way, so that the compiler will catch `missing includes`.

1.   The paired header file (ex: if add.cpp, paired is add.h)
2.   Other headers from your project
3.   3rd party library headers
4.   Standard library headers

The headers for each grouping should be sorted alphabetically.

## Where to keep header file

Header files should either be store in the same directory of the code file that import it,  
or in subdirectory in the file system of the project.

Specify which directories to look for when compiling with the -I flag:
> g++ -o main -I/source/headerDir

## Good practices
- Always include header guards
- Do not define variables and functions in header files.
- Give a header file the same name as the source file it’s associated with (ex: add.cpp header is add.h).
- Each header file should have a specific job, and be as independent as possible.
- Be mindful of which headers you need to explicitly include for the functionality that you are using in your code files.
- Every header you write should compile on its own (it should #include every dependency it needs).
- Only #include what you need (don’t include everything just because you can).
- Do not #include .cpp files.

