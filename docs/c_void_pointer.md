# C void pointer

Also called a `generic pointer`. 

The void pointer `void*` is a pointer with no associated data type.

- It can hold an address of any type
- It can be typecasted to any type
- It `cannot` be dereferenced

```c
int a = 1;
char b = 'd';
void *p = &a;
p = &b;

// typecast to another pointer when used
printf("%c", *(int*)p);

printf("%c", *p); // !! won't work, cannot be dereferenced
```

## Pointer arithmetic with void*

Is allowed in `gnu C` but `NOT` in the C standard. So compile with `gcc`.

```c
char *str = "Hello there";

void *p = str;

p = p + sizeof(char);

printf("%c", *(char*)p); // 'e'
```

## void* for generic function parameter

```c
// function that return any sort of pointer
void *alocate(sizeof(int));

// function that take any sort of pointer and dealocate it.
int dealocate(void* p);
```

## void* for function pointer

Void* can be used to create a pointer to a function without specifying its return type or parameter type explicitly.
Allows versatile functions, that take another function parameter as a callback.

```c
// take a fonction that take any sort of argument
int time_function( int(*cb)(void*), void* arg) { 
  timer_start();
  
  // Call the callback function with the provided argument
  (*cb)(arg);
  
  timerstop();
  return timer_diff();
}

int test(int *p);
int a = 2;

// Calling time_function with the test function as a callback
// 'test' is casted to int(*)(void*) to match the expected function pointer type
time_function( int(*)(void*)test, (void*)&a)
```
> `!!` `int (*cb)(void*)` != `int *cb(void*)` the first is a pointer to a function that return an int, the second is a function that return a int*

