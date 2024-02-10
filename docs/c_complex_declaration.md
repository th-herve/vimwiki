# C complex declaration

How to read stuff like this: `char* (*(*foo[5])(char*))[];`

To read complex declaration follow those rules to get the order:

1. Parentheses grouping elements
2. Postfix operator `()` indicating a function, and `[]` an array
3. Prefix operator `*` indicating a pointer to

## Examples

### char* foo[5];

The precedence order is `[]`, `*`, `char`

1. `[5]` = foo is an array of 5
2. `*` = pointer to
3. `char` = char

Giving : `foo is an array of 5 pointer to char`

### char(* foo)[5];

The precedence order is `(*foo)`, `[5]`, `char`

1. `(* )` = foo is a pointer to
2. `[5]` = an array of 5
3. `char` = char

`foo is a pointer to an array of 5 char`

### char* (*foo)(char*);

1. `(*foo)` = foo is a pointer to
2. `(char*)` = to a function taking a char*
3. `char*` = returning a char*

`foo is a pointer to a function taking a char* and returning a char*`

### char* (*(*foo[5])(char*))[];

1. `foo[5]` = foo is an array of 5
2. `*foo` = pointer to
3. `(char*)` = function that take a char*
4. `(*()())` returning a pointer to 
5. `(()())[]` an array
6. `char*` of char*

`foo is an array of 5 pointer to a function that take a char* as argument and return a pointer to an array of char *`

[source](https://medium.com/@bartobri/untangling-complex-c-declarations-9b6a0cf88c96)
