# === C++ ===

## Variable

### declaration

```cpp
int a;
int b;
```
## assignment

```cpp
int width;
width = 5;
```

### Initialization

Declaration + assignment.  
Can be complex in C++

```cpp

int a;         // no initializer (default initialization)
int b = 5;     // initializer after equals sign (copy initialization)
int c( 6 );    // initializer in parenthesis (direct initialization)

// List initialization methods (C++11) (preferred)
int d { 7 };   // initializer in braces (direct list initialization)
int e = { 8 }; // initializer in braces after equals sign (copy list initialization)
int f {};      // initializer is empty braces (value initialization)

```
copy initialization, `int b = 5;` less common in C++ because less efficient  
direct initialization, `int c(5)`
List initialization using {} are more common. Have the benefit to disallow narrowing conversion. (ex: int width{4.5} == error)


## operator

| operator | name             | action                                                              | exemple              |
|----------|------------------|---------------------------------------------------------------------|----------------------|
| <<       | insertion        |                                                                     | std::cout << "hello" |
| >>       | extraction       |                                                                     | std::cin >> x        |
| ::       | scope resolution | identifies on the left, the namespace of the right identifier       | std::cout            |


```cpp

```
