# C++ stacks

Stack sacrifice the flexibility of other data structures for 
more systematic interactions eith the data.

It mimic a physical stack and operate in a `LIFO` context.
Each elements added to the stack is both the top and bottom of the stack.

The only element that can be removed is the top one.

## Creating a stack

Include the `stack` library.

```cpp
#include <stack>

```
Create with:

std::stack[<type>] [name];

```cpp
std::stack<int> my_numbers;
```
> The type cannot be changed after declaration.

### Stack methods

### Add elements

Use `.push()` to insert a new element at the top.

```cpp
my_numbers.push(2);
my_numbers.push(6);
```
### Remove elements

Use `.pop()` to removes the top element.

```cpp
my_numbers.pop();
```

### Access element

Use `.top()` to access the top element (only element accessible).

```cpp
my_numbers.top();
```

### Size of a stack

Use `.size()` to get the number of elements in a stack.

```cpp
std::cout << my_numbers.size();
```

Use the `.empty()` function to know if a stack is empty or not.
Return `0` if empty, `1` otherwise.
