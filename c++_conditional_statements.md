# C++ Conditional statements

## if-else

- if
- else
- else if

### Shorthand if-else

Condense an `if-else` expression in a single statement.

```cpp
variable = (condition) ? value_if_true : value_if_false;
```

### Omitting brackets

Curly brackets`{}` can be omitted if there is only one statement inside
an `if`, `else if` or `else` block.

```cpp
if (number == 7)
    std::cout << "nice";
    
if (number == 7) {
    std::cout << "nice too";
    }
```

` ` It is better to not ommit the brackets.


## switch statement

```cpp
switch (grade) {
    case 9:
        std::cout << "Freshman";
        break;
    case 10:
        std::cout << "Sophomore";
        break;
    default:
        std::cout << "Invalid";
        break;
}
```

If the `break` keyword was ommited, and the value of grade `9`, the case `10`
would also be executed. 
This type of bug is called a `fallthrough`.


