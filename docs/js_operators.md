# Javascript operators

## Arithmetic operators

| operator | description    |
|----------|----------------|
| +        | addition       |
| -        | subtraction    |
| *        | multiplication |
| **       | exponentiation |
| /        | division       |
| %        | modulus        |
| x++      | post-increment |
| x--      | post-decrement |
| ++x      | pre-increment  |
| --x      | pre-decrement  |

## Assignment operators

| operator | description    |
|----------|----------------|
| =        | Assignment     |
| +=       | Addition       |
| -=       | substraction   |
| *=       | multiplication |
| /=       | division       |
| %=       | remainder      |
| **=      | exponentiation |

## Comparison operators

| operator | description                       |
|----------|-----------------------------------|
| ==       | equal to                          |
| ===      | equal value and type              |
| !=       | not equal                         |
| !==      | not equal value or not equal type |
| >        | greater than                      |
| <        | less than                         |
| >=       | greater than or equal to          |
| <=       | less than or equal to             |



## Logical operators

| operator | description |
|----------|-------------|
| &&       | and         |
| ∣∣       | or          |
| !        | not         |

In Javascript, logical operator offer more feature than just manipulating boolean values.

### ∣∣ operator

In this statement, the or operators work as follow.

```js
let value1 = "";                     // false
let value2 = "";                     // false
let value3 = "hello";                //true
result = value1 || value2 || value3; // return value3
```

- Evaluates operands from left to right.
- Convert each operand to a boolean:
    - If `true`, it stops and return the original value of that operand.
    - If all operands are `false`, it return the last one.

### && operator

The and operator work similarly to or, but return a false value.

- Evaluates operands from left to right.
- Convert each operand to a boolean:
    - If `false`, it stops and return the original value of that operand.
    - If all operands are `true`, it return the last one.

