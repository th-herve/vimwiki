# C preprocessor directive

Create symbolic constants.

```c
#define NAME REPLACEMENT

// example

#define PI 3.14159265

main()
{
  int a = PI * 2;
}
```
When compiled, NAME is replace with REPLACEMENT.

> Note: There is no semicolon at the end
