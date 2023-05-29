# C++ function

```cpp
void functionName() {
    std::cout << "function are great";
}
```

## Parameters and arguments

### Parameters

`Parameters` are defined in the funtion declaration, inside the parentheses `()`.

Contain a `name` and `datatype`.

```cpp
int feetToInches(int ft) {
    return ft * 12;
}
```

### Argument

Value passed to the function when performing a function call.

```cpp
test = feetToInches(6);
```

### Default parameters

```cpp
void message(std::string language = "C++") {
    std::cout << "I like" << language;
}

int main() {
    message();
    message"java";
}
```

### Pass by reference

Allows a function to modify the velue of its argument.

Use the `&` operator.

```cpp
void plusFive(int& i) {
    i += 5;
}

int main() {
    int j = 10;
    plusFive(j);
    // j == 15
}
```

## Function overloading

`Function overloading` allows multiple functions to have the same name
as long as they differ in their parameters.

It enables functions to handle different types/numbers of inputs.

```cpp
int add(int a, int b) {
    return a + b;
}

int add(double a, double b) {
    return a + b;
}
```

To be overlaoded, functions should have at least one of the following properties:

- Each functions has a different types of parameters
- Each functions has a different number of parameters

