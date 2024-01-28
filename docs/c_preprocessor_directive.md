# C preprocessor directive

## define 

Also called `macro subtitution`. Create symbolic constants.
Its scope start when declared and stop at the end of the file.
`#undef` can be used to remove the macro.

```c
#define NAME REPLACEMENT
// ..
#undef NAME

// example
#define PI 3.14159265


main()
{
  int a = PI * 2;
}

// more complex example

#define forever for(;;)

#define max(A, B) ((A) > (B) ? (A) : (B))

int x = max(1, 2)
```
When compiled, NAME is replace with REPLACEMENT.


## include

```c
// < > mostly for system files
#include <stdio.h>

// " " mostly for user's programs or files
#include "foo.h"
```
