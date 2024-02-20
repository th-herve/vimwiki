# C typedef

Use to give a type a new name.  
By convention the new name is capitalize.

```c
typedef char *String;

String str = "hello there";
```

## Renaming a struct

```c
typedef struct node {
  // ...
} Node;
```

##  Function type

```c
// type for function taking a char* and returning an int
typedef int (*Func)(char *);

Func myFunction;
```

## Other uses

- Change type depending on os requirement. Instead of changing the size of an int everywhere depending on the os, only one typedef can be changed.
- Better documentation.
