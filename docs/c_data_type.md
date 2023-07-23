# C datatype

# integer

Take up `4 bytes` of memory (32 bit).
Negative and positive.

```c
int number = 9;
int number1, number2;
```

## Unsigned integer

Also take up `4 bytes`.

Double the positive value an integer can hold.
But remove the negative the possibilities of holding negative.

It is a `qualifier`.

## short and long

TODO

# Char

Take `1 byte` (8 bits)
The Ascii standard map the positive value of a char to a symbol.

## Float

Take up `4 bytes` of memory (32 bits).
Due to this size limitation, they can be `unprecise`.

## Double

Take up `8 bytes` (64 bits).
Better than float when precision is needed.

# Void

Void is a `type` but NOT a datatype. Meaning we can create a variable of type void.

# Bool

Not default in C, must be included.

```c
#include <stdbool.h>
```

# String

Not directly included in C.

```c
// Character array
char str1[] = "Hello";

// string literal
const char* str3 = "This is a string literal"; // cannot be modified
```
