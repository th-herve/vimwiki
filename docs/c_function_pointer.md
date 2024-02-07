# C function pointer

```c
void print(int a) { ... };

// pointer to the function, named fp
void (*fp)(int) = print; // we can use print or &print, with the same result

// call with the pointer
(*fp)(2);
fp(2); // same thing
```

## Array of function pointer

```c
int add(int a, int b) {...};
int sub(int a, int b) {...};

// creation of the array of function
int (*fArr[])(int, int) = {add, sub};

// call to sub
int res = (*fArr[1])(2, 3);
```

Example from dwm source code:

```c
// with an enum that match each value in between []
static void (*handler[LASTEvent]) (XEvent *) = {
	[ButtonPress] = buttonpress,
	[FocusIn] = focusin,
	[KeyPress] = keypress,
	[MapRequest] = maprequest,
};
```

## Passing function pointer as function argument

```c
void fn1(int a) {...};
void fn2(int a) {...};

void wrapper(void (*fn)(int))
{
  fn(); // call the function in passed in argument
}

// call to wrapper
wrapper(fn1);
wrapper(fn2);
```

[More detail](https://www.geeksforgeeks.org/function-pointer-in-c/)
