# C++ loops

- while
- do-while
- for
- for-each

## while

```cpp
int count = 1;

while (count <= 5) {
    std::cout << count;
    count ++;
}
```

## do-while

```cpp
int price = 300;

do {
    std::cout << "Too expensive";
} while (price > 500);
```

## for

```cpp
for (int i = 1; i<=n; i++) {
    std::cout << i;
}
```

## for-each

```cpp
int my_list[5] = {0, 1, 2, 3, 4};

for (int number : my_list) {
    std::cout << number;
}
```

The counter variable can be declared with `auto` keyword.

C++ deduce the type based on the type of the list

```cpp
int my_list[5] = {0, 1, 2, 3, 4};

for (auto number : my_list) {
    std::cout << number;
}
```

## break and continue

### break

The `break` keyword is used to jump out of a loop.

```cpp
for (int i = 0; i < 10; i++) {
    if (i == 4) {
        break;
    }
    std::cout << i;
}
```

Difference between `break` and `return`

- `break` terminates a `switch` or `loop`, code execution continue at the line after the sciwch or loop.
- `return` terminates a `function`, code execution continue where the function was called.

### continue

Skip an iteration of a loop. If `continue` is executed, the loop skip the iteration and goes to the next.

```cpp
for (int i = 0; i < 10; i++) {
    if (i == 4) {
        continue;
    }
    std::cout << i;

```
