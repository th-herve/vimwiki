# C++ operators

## Arithmetic operators

| operator | name           |
|----------|----------------|
| +        | addition       |
| -        | substraction   |
| *        | multiplication |
| /        | division       |
| %        | modulus        |

| operator | name           | example | description                                    |
|----------|----------------|---------|------------------------------------------------|
| ++x      | pre-increment  | ++5     | first increment x then return x                |
| --x      | pre-decrement  | --5     | first decrement x then return x                |
| x++      | post-increment | 5++     | first copy x then increment x then return copy |
| x--      | post-decrement | 5--     | first copy x then decrement x then return copy |


### Pre vs post-increment/decrement

When place before the operand, it is a `pre-increment/decrement` operator.

1. The value of the operand is incremented/decremented
2. The new operand value is returned.


```cpp
int x = 10;

// x is decremented to 9, then assigned to y
int y = --x;

std::cout << x << ' ' << y;

//output: 9 9
```


When place after the operand, it is a `post-increment/decrement` operator.

1. The value of the operand is copied
2. The operand (not the copy) is incremented/decremented
3. The copy (not the original value) is retured


```cpp
int x = 10;

// a copy of x is made, x is decremented to 9
// the value of the copy (10) is assigned to y
int y = x--;

std::cout << x << ' ' << y;

//output: 9 10
```


## Assignment operators

Operators that assign value to a variable.


| operator | example        |
|----------|----------------|
| =        | x = 5          |
| +=       | x += 5         |
| -=       | x -= 5         |
| *=       | x *= 5         |
| /=       | x /= 5         |
| %=       | x %= 5         |

## Relational operators

Compare two variables or values.

The result of the operation is a `bool`.

| operator | example |
|----------|---------|
| ==       | x == y  |
| !=       | x != y  |
| >        | x > y   |
| <        | x < y   |
| >=       | x > y   |
| <=       | x < y   |

## Logical operators

Compare the logic of two or more conditions.

The result of the logical operation is a `bool`.

| operator | example |
|----------|---------|
| &&       | x == y  |
| ∣∣       | x ∣∣ y  |
| !        | !x      |

## Special operator

| operator | name             | action                                                              | exemple              |
|----------|------------------|---------------------------------------------------------------------|----------------------|
| <<       | insertion        |                                                                     | std::cout << "hello" |
| >>       | extraction       |                                                                     | std::cin >> x        |
| ::       | scope resolution | identifies on the left, the namespace of the right identifier       | std::cout            |


```cpp
std::cout << "hello there" << name;
std::cin >> variable_name;
```


## Bitwise operators

Manipulate variables at bit level.

Commonly used with numerical variables.

| operator | name        | example | description                     |
|----------|-------------|---------|---------------------------------|
| <<       | left shift  | x << y  | shift bits in x left by y       |
| >>       | right shift | x >> y  | shifht bits in x right by y     |
| ~        | bitwise NOT | ~x      | flip all bits in x              |
| &        | bitwise AND | x % y   | each bit in x AND each bit in y |
| ∣        | bitwise OR  | x ∣ y   | each bit in x OR each bit in y  |
| ^        | bitwise XOR | x ^ y   | each bit in x XOR each bit in y |

> More [info](https://www.codecademy.com/resources/docs/cpp/bitwise-operators)

## Operator precedence

In a compound expression, operators are evaluated in the order of their precedence level 
in descending order (smallest precedence value go first).

Find the complete list [here](https://en.cppreference.com/w/cpp/language/operator_precedence).
