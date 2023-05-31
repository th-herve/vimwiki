# C++ intro

Computer execute machine language(or instruction): 0 and 1

Assembly language: each instruction is identified by a abbrevation 
A program called assembler, translate it in machine language.

High level language such as C/C++, must be transormed. This is done with `compiling` and `interpreting`

A compiler read source code and produces stand alone executable program that can be run.  
[diagram](https://www.learncpp.com/images/CppTutorial/Chapter0/Compiling-min.png?ezimgfmt=rs:521x161/rscb2/ng:webp/ngcb2)

A interpreter is a program that directly execute the instructions in the source code. Without requiring them to be compiled.  
They tend to be more flexible than compilers but less efficient because it needs to be done each time the program run.


## C++ development 

1. Define the problem to solve: What step
2. How to solve: How step, do not just start coding. 
    # good solutions tend to be:
        1. straightforward
        2. well documented
        3. built modularly, can be reused or changed without impacting other part of the program
        4. robust, 
3. Write the program
4. Compile the source code:
    The complier make two important thing:
        1. make sure that there is no error
        2. translate the source code into machine language called object file (.o or .obj), there is as many .o files as .cpp
5. Linking object files and libraries:
    Combine the objects files and libraries into one executable program. It also check that all cross file dependencies are resolved.
6. Test and debug!


## Compiler configuration

A `build configuration` (or build taget), is a collection of settings that determines how to build a project.  
Contain info like, executable name, libraries to look for, how much optimization to make...  
Two main configuration:
    1. Release 
    2. Debug
