# C++ command line arguments

## Passing command line arguments

Pass them after the executable name
> g++ greeting.cpp -o greeting
> ./greeting commandLineArgument

> Note: command line arguments are `always` passed as `string`

## using command line arguments


```cpp
int main(int argc, char* argv[]);
// or
int main(int argc, char** argv);
```


- `argc`: argument count, `int` parameter containing the number of command line arguments. Its value is always at least 1 because the name of the executable is treated as an argument.
- `argv`: argument verctor, `array` containing the value of command line arguments. Range from `0` to `argc -1`


```cpp
#include <iostream>

int main(argc, char* argv[]) {
    for(int i = 0; i < argc; i++) {
        std::cout << argv[i];
    }
    return 0;
}
```


