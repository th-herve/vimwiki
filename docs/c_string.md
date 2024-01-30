# C string

String do not exist in c. It's instead represented as succession of char terminated by the null character `\0`.

There is two ways to represent string:

- a pointer to a string literal: the string cannot be modified
- an array of char: each char can be manipulated like in an array

```c
// using an array
char str[] = "boo"; // string literal is converted to an array and add the null char
char str[] = {'b', 'o', 'o', '\0'}; // equivalent

// using a pointer
char *str = "boo";
```
