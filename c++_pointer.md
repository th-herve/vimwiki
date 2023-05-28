# C++ pointer

A `pointer` is a variable that stores a memory address as its value.  
Pointer are declared with an asterisk `*` between the data type and the variable name.

It must point to a data type of the same type. 

It is usually assigned with the `&` operator. That obtain the address of a variable. 

` ` Pointer must be initialized before being used.
` ` Avoid pointers if possible. Prefere `references`.

***
```cpp
int my_var = 5;

int* my_ptr = &my_var;
```
***

When the value of the pointer changes, the value of the original variable change
in the same way.

## Dereference

When `not` used in a declaration, the asterisk symbol `*` is called the 
`dereference` operator. 

It is used to obtain the value pointed by a pointer.

***
```cpp
// print the address (0x7ffd1d8306c4)
std::cout << my_ptr;

// print the value pointed at
std::cout << *my_ptr;

// same result as *my_ptr
std::cout << my_var;
```
***

## Null pointer

` `Do not leave a pointer variable uninitialized.

If not use, assign it to `nullptr` keyword.

***
```cpp
int* ptr = nulptr;
```
***
