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

## condional inclusion

Use `#if`,  `#elif`, `#else` 

`#ifdef` and `#ifndef` test if a  name is defined or not.
> the keyword `defined(name)` can also be used: `#if defined(NAME)`

```c
// make sure that boo.h is included only once
#ifndef HDR

#define HDR

// hdr.h content

#endif
```

```c
// decide which file to include
#if SYSTEM == SYSV
  #define HDR "sysv.h"
#elif SYSTEM == BSD
  #define HDR "bsd.h"
#else
  #define HDR "defaut.h"
#endif

#include HDR
```
