# Variables

## Declaration, assignment and initialization

While similar, there is important distinction between those concept.
It apply to class, function, variable...

In the case of variable:

- Declaration: State a type and a name, but not a value. Memory will be allocated to it.
- Assignment: It is giving to an already `declared` variable, a value.
- Initialization: declaring + assignment at the same time.

## Declaration

[type] [name];

```cpp
int a;
int b;
```
## Assignment

[name] = [value]

```cpp
// declaration
int width;

// assignment
width = 5;
```

## Initialization

Declaration + assignment.  
Can be complex in C++
The value given to initialized the variable is called `initializer`

Use this method:
```cpp
int a { 7 };
```

Four basics ways:

- `Default initialization`: No initializer provided
- `Copy initialization:` Initialization with assignment operator`=`
- `Direct initialization`: Value provided inside parenthesis `()`
- `List initialization`: Value provided inside Brackets `{}`


```cpp
int a;         // no initializer (default initialization)
int b = 5;     // initializer after equals sign (copy initialization)
int c( 6 );    // initializer in parenthesis (direct initialization)

// List initialization methods (C++11) (preferred)
int d { 7 };   // initializer in braces (direct list initialization)
int e = { 8 }; // initializer in braces after equals sign (copy list initialization)
int f {};      // initializer is empty braces (value initialization)

```
List initialization using {} are more common and have the benefit to disallow narrowing conversion. (ex: int width{4.5} == error)

## Initializing multiple variables

```cpp
int a = 5, b = 6;          // copy initialization
int c( 7 ), d( 8 );        // direct initialization
int e { 9 }, f { 10 };     // direct brace initialization (preferred)
int g = { 9 }, h = { 10 }; // copy brace initialization
int i {}, j {};            // value initialization
```
> Note: the type is given one time only

### Constant variables

Variable whose value cannot be changed after initialization.

Use the `const` keyword

```cpp
const double pi = 3.14;
```
> Constant variable must be initialized (assign a value) when declared.
 
