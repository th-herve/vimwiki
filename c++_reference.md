# C++ reference

Provides ways to directly manipulate memory.
It bring many used  cases such as dynamic memory allocation and advanced data structures.

## Reference

In c++, a `reference` variable is an alias to an existing variable.
It is declared with an ampersand `&` between the reference type and the variable name.

It is primary use in `function parameter`.  
It allow function to modify the value of the variable referenced.


```cpp
int exam_grad = 85;
int& score = exam_grade;
```


>Note: this notation is correct too `int &score = exam_grade;`

The `score` variable is an alias to `exam_grade` variable.  
When the value of `score` is changed, the value of `exam_grade` change in the same way. 

` ` Be careful of two things when declaring reference variable:

- References must be `initialized`
- References `cannot` be `reassigned`

### Pass-by-reference

Reference can be initialized in function parameter. Allowing easy manipulation of the 
original variable.


```cpp
void add_five(int& i) {
   i += 5; 
}

//In main
int a = 100;
add_five(a);

// a = 105
```


## Memory address

When `not` used in a declaration, the ampersand `&` si called the
`adress of` operator and is used to access the memory address of a variable.


```cpp
int exam_grad = 85;
std::cout << &exam_grade;
```


