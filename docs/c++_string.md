# C++ string library

String, like in `C`, are not a built in type. They must be included with 
a library.

### Include

```cpp
#include <string>
```

### Declare a string

```cpp
std::string variable_name = "hello there";
```

### String method

#### Concatenation

Use the `+` opertor.


```cpp
std::string message = "hello" + variable + ".";
```


#### Access specific character

Use the `[]`.


```cpp
std::string my_string = "hello there";

char letter = my_string[2];
```


#### length()


```cpp
std::string my_string = "hello there";

int string_length = my_string.length()
```


