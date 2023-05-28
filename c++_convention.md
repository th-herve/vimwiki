# === C++  convention ===

Based on [this](https://www.codecademy.com/courses/c-plus-plus-for-programmers/articles/cpp-style-guide)

Following [Google C++ sytle guide](https://google.github.io/styleguide/cppguide.html#cpplint)

## == Naming convention

Name never start with digit

Can't use a predifiend keyword

User defined `class` and `function` use `PacalCase` 
> `LinkedList` or `BubbleSort()`

`Variable` uses `snake_case` 
> `student_id` or `result`

## == Punctuation marks ==

- Brackets `{}`: 
    - Open bracket on the same line as the statement. 
    - Closing bracket under the last line.
- Parentheses `()`: 
    - No space between parenthesis and the code inside
    - In a statement, space before `(` and after `)`
    - In class or function, space after `)` only

Example: 

***
```cpp
int GetLargerNumber(int num_one, int num_two) {
    if (num_one > num_two) {
        return num_one;
    }
    else {
        return num_two;
    }
}
```
***

## == Formatting ==

### Spacing

- Types, variable, operators and literal value, separated by one horizontal space. 

***
```cpp
string message = "hello world";
```
***

- Classes, functions, global variables declaration and preprocessor directives, separated by one vertical space.

***
```cpp
#include <iostream>    // preprocessor directive
 
float pi = 3.1415;    // global variable
 
class MyClass {        // class
  public:
    myClass() {
  }
};
 
int main() {        // function
  return 0;
}
```
***

### Indentation

Each new block (loop, method...) opening should be intended.

### Line length 

- 80 characters
