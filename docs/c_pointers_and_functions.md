# C pointers and functions

## Pointers as function arguments

In c, function arguments are passed by value. Unless passed as a pointer.

```c
void swap(int *px, int *py) {
  int temp = *px;
  *px = *py;
  *py = temp;
}

// call it with the reference of the objects
int a = 1, b = 2;
swap(&a, &b);
```

