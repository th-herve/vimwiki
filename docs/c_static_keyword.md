# C static keyword

In C, the `satic` keyword has several utility.

## Static variable

Inside a function, the static keyword make a variable retains its value between function calls.
But its scope stay local.

```c
// count the number of times the function is called. Each called, the value of the count is retains and incremented
int counter() {
  static int count = 0;
  count++;
  
  return count;
}
```
## Static global variable

When declared with a global variable, it make this variable only available in the file it's in.

```c
static int foo = 2;

int main(void) {
  //...
}
```

## Static function

Used with a function, it make it only available in the file it's in.

```c
static void boo() {
  // ...
}
```
