# Stdio.h

```c
#include <stdio.h>
```

## printf

```c
int num = 2;
printf("num = %d\n", num);
```

| Format Specifier | Description             | Example                  |
|------------------|-------------------------|--------------------------|
| %d               | Integer                 | printf("%d", 42);        |
| %f               | Float/Double            | printf("%f", 3.14);      |
| %c               | Character               | printf("%c", 'A');       |
| %s               | String                  | printf("%s", "Hello");   |
| %p               | Pointer                 | printf("%p", &variable); |
| %x               | Hexadecimal (lowercase) | printf("%x", 255);       |
| %X               | Hexadecimal (uppercase) | printf("%X", 255);       |
| %o               | Octal                   | printf("%o", 63);        |
| %u               | Unsigned Integer        | printf("%u", 42);        |
| %e               | Scientific Notation     | printf("%e", 123.45);    |
| %E               | Scientific Notation     | printf("%E", 123.45);    |
| %g               | Shorter of %f and %e    | printf("%g", 123.45);    |
| %G               | Shorter of %f and %E    | printf("%G", 123.45);    |
| %%               | Literal %               | printf("%%");            |
