# C++ vector

`Vector` are similar to arrays but can dynamically change size.

## Create a Vector

Include the `vector` library and create a vector with:

std::vector<type> <name>;

```cpp
#include <vector>

std::vector<char> alphabet;
// or
std::vector<char> alphabet = {'a', 'b', 'c'};
```
> Note: the type cannot be changed after its declaration.

## Vector methods

### Add elements

Add element at the `end` of a vector with `.push_back()`

```cpp
std::vector<int> my_numbers;
my_numbers.push_back(2);
my_numbers.push_back(6);

// my_numbers contains {2, 6}
```

### Remove elements

Remove the `last` element with `.pop_back()`.

```cpp
my_numbers.pop_back();
```

## Accessing elements

Access a given index with brackets `[]`

```cpp
std::cout << my_numbers[2];
```

Access the first and `last` and `first` element with `.front()` and `.back()`

```cpp
std::cout << my_numbers.front();
std::cout << my_numbers.back();
```

## Vector size

Get the number of elements with `.size()`

```cpp
std::vector<std::string> colors = {"Red", "Green", "Blue"};

std::cout << colors.size(); // outputs: 3
```
`.empty()` return 0 if a vector is empty and 1 otherwise.


## Iterating over a vector

Use `for` loop (with vector.size()) or a `for-each` loop.
