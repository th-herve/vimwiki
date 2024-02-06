# C pointers and arrays

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

## Array of pointers

```c
// create an array of int*
int a=1, b=2, c=3;
int *str[&a, &b, &c];
int d = *str[1]
```
