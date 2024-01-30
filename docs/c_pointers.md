# C pointers

The unary operator `*` dereferences a pointer.
The unary operator `&` gives the address of an object.

```c
int x = 1, y = 2, z[10];

int *ip;          // ip is a pointer to int

ip = &x;          // ip now points to x

y = *ip;          // y is now 1

*ip = 0;          // x is now 0

ip = &z;[0];      // ip now points to z[0]
```

If a pointer p points to x, it can occurs whenever x would be used

```c
*p = *p + 10;

*p += 1;

(*p)++; // without parenthesis, the pointer would be incremented, not the value it points to.
```
> Note: C guarantees that 0 is never a valid address. Thus `int *p = 0` is consider an empty pointer.
> 0 can be replace by `NULL` for more clarity by including `<stdio.h>`

## Pointers as function arguments

In c, function arguments are passed by value. Unless passed as a pointer.

```c
void swap(int *px, int *py) {
  int temp = *px;
  *px = *py;
  *py = temp;
}

// call it with the reference of the objects
swap(&a, &b);
```

## Pointers and arrays

Array can be manipulated, sometimes more efficiently with pointers.

```c
int a[10];
int *pa;

pa = &a[0]; // pa points to the first element of a
pa = a // yield the same result

x = *pa; // set x to a[0]

y = *(pa+1) // set y to a[1]
```

## Pointers arithmetic

If p is a pointer to an element of an array, `p++` point to the next elements. 
`p += i` points i elements beyond what p does.

If p and q are both pointer to the same array. Comparison operators like ==, <=, != can be used:

```c
if (p > q) {...
```
> Pointers can also be compared for equality with 0, but not with pointers from a different array.

Integer can be added or subtracted to pointers. The integer value is converted to the number of bytes of the data type:

```c
int *p = &a[0];

p+3 // is really p + 3*sizeof(int)
```

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
