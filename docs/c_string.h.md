# String.h

```c
#include <string.h>
```

## strlen

Return the size `size_t` of a string, excluding the `\0`.

```c
char word[20] = "hello there";

printf("Length of string word = %zu \n", strlen(word)); // %zu print a size_t

```
