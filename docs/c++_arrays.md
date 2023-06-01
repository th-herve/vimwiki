# C++ arrays

An `array` is a fixed-sized collection of items of the `same type`.

## Create an array

Specify the type, name and size in brackets.

```cpp
int my_numbers[5];
```
Initialize the values when created with braces `{}`.
The size in bracket can be omitted.

```cpp
int my_numbers[5] = {1, 2, 3, 4, 5};
// or
int my_numbers[] = {1, 2, 3, 4, 5};
```

## Accessing/modifying array elements

```cpp
std::cout << my_numbers[2];

my_numbers[2] = 7;
```
## Multidimensional arrays

Create an array of arrays or multidimensional arrays.

```cpp
int table[3][5] = {
  {0, 1, 2, 3, 4} ,     //initializers for first row
  {5, 6, 7, 8, 9} ,     //initializers for second row
  {10, 11, 12, 13, 14}  //initializers for third row
};
```

## Iterating through and array

Use a `for` loop or `for-each` loop.
Use nested loop for multidimensional arrays.
