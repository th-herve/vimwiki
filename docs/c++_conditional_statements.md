# C++ Conditional statements

## if-else

- if
- else
- else if

### Ternary operator

Or shorthand if-else.

Condense an `if-else` expression in a single statement.

[(type)] [variable] = [condition] ? [value_if_true] : [value_if_false];


```cpp
int number = 10;

std::string is_10 = (number == 10) ? "yes" : "no";

```

### Omitting brackets

Curly brackets`{}` can be omitted if there is only one statement inside
an `if`, `else if` or `else` block.

```cpp
if (number == 7)
    std::cout << "nice";

// same as:
if (number == 7) {
    std::cout << "nice too";
    }
```

`⚠` It is better `not` to ommit the brackets.


## switch statement

```cpp
int grade = 9;

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

If the `break` keyword was ommited, and the value of grade was `9`, the case `10`
would also be executed. 
This type of bug is called a `fallthrough`.


