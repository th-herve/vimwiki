# C++ queue

A `queue` mimic a physical queue. Each new object become the back of the queu,
the object at the front will always leave the queue first.

Operate in a `FIFO` context.

## Create a queue

Include the `queue` library.

```cpp
#include <queue>

std::queue<std::string> waiting_line;
```
> Note: the type of the queue cannot be changed after the declaration.

## Queue methods

### Adding methods

Use `.push()` to insert a new element at the end of the queue.

```cpp
waiting_line.push("Bob");
```

### Removing an element

Use `.pop()` to removes the oldest element.

```cpp
waiting_line.pop();
```

### Access an element

Only the first and last element are accessible.
Use `.front()` and `.back()`

```cpp
std::cout << waiting_line.front();
std::cout << waiting_line.back();
```

### Size of a queue

Use `.size()` to get the number of element.

Use `.empty()` to know if a queue is empty or not.
Return `0` if empty, `1` if not.
