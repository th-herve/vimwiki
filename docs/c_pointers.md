# C pointers

The unary operator `*` dereferences a pointer.
The unary operator `&` gives the address of an object.

```c
int x = 1, y = 2, z[10];

int *ip;          // ip is a pointer to an int

ip = &x;          // ip now points to x

y = *ip;          // y is now 1

*ip = 0;          // x is now 0

ip = &z[0];      // ip now points to z[0]
```

If a pointer p points to x, it can occurs whenever x would be used

```c
*p = *p + 10;

*p += 1;

(*p)++; // without parenthesis, the pointer would be incremented, not the value it points to.
```
> Note: C guarantees that 0 is never a valid address. Thus `int *p = 0` is consider an empty pointer.
> 0 can be replace by `NULL` for more clarity by including `<stdio.h>`

## Fetch pointer and increment it

A common operation is to fetch the value of a pointer, then move it by incrementing it.  
A compact way to do it is `*p++`

```c
void movePointer(char *p) {

  char i;

  // i take the current value of p, then p is moved to its next value. Since a char* is terminated by \0, the loop stop at the end of the pointer.
  while(i = *p++) {
    printf("%c", i);
  }
  
}
```
