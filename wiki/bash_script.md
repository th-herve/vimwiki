# Bash script

# Basic Syntax

Bash scripts are typically written in a plain text file with a .sh extension. The first line of the file should specify the interpreter that should be used to execute the script. For example, the following line would specify that the Bash shell should be used:

```bash

#!/bin/bash

```
After specifying the interpreter, you can start writing your Bash script. Bash commands can be executed in a script just like they would be in a terminal. For example, the following script would print "Hello, world!" to the terminal:

```bash

#!/bin/bash

echo "Hello, world!"
```

# Control Flow Statements

Bash provides several control flow statements that allow you to execute different parts of your script based on certain conditions. Here are some of the most commonly used control flow statements:

## If Statements

If statements allow you to execute code based on whether a certain condition is true or false. The basic syntax for an if statement is as follows:

```bash

if [ condition ]; then
  # Code to execute if condition is true
fi
```

Here's an example of an if statement that checks whether a number is greater than 10:

```bash

#!/bin/bash

num=15

if [ $num -gt 10 ]; then
  echo "$num is greater than 10"
fi
```

## Else Statements

Else statements allow you to execute code if the condition in an if statement is false. The basic syntax for an else statement is as follows:

```bash

if [ condition ]; then
  # Code to execute if condition is true
else
  # Code to execute if condition is false
fi
```
Here's an example of an if-else statement that checks whether a number is greater than 10:

```bash

#!/bin/bash

num=5

if [ $num -gt 10 ]; then
  echo "$num is greater than 10"
else
  echo "$num is less than or equal to 10"
fi
```
## Elif Statements

Elif statements allow you to check multiple conditions in a single if statement. The basic syntax for an elif statement is as follows:

```bash

if [ condition1 ]; then
  # Code to execute if condition1 is true
elif [ condition2 ]; then
  # Code to execute if condition2 is true
else
  # Code to execute if both condition1 and condition2 are false
fi
```
Here's an example of an if-elif-else statement that checks whether a number is positive, negative, or zero:

```bash

#!/bin/bash

num=-5

if [ $num -gt 0 ]; then
  echo "$num is positive"
elif [ $num -lt 0 ]; then
  echo "$num is negative"
else
  echo "$num is zero"
fi
```

## For Loops

For loops allow you to execute a block of code for each item in a list. The basic syntax for a for loop is as follows:

```bash

for variable in list; do
  # Code to execute for each item in list
done
```
Here's an example of a for loop that prints the numbers 1 through 5:

```bash

#!/bin/bash

for i in 1 2 3 4 5; do
  echo $i
done
```
## While Loops

While loops allow you to execute a block of code repeatedly as long as a certain condition is true. The basic syntax for a while loop is as follows:

```bash

while [ condition ]; do
  # Code to execute while condition is true
done
```
Here's an example of a while loop that counts from 1 to 5:

```bash

#!/bin/bash

count=1

while [ $count -le 5 ]; do
  echo $count
  count=$((count+1))
done
```
## Case Statements

Case statements allow you to execute different code blocks based on the value of a variable. The basic syntax for a case statement is as follows:

```bash

case variable in
  pattern1)
    # Code to execute if variable matches pattern1
    ;;
  pattern2)
    # Code to execute if variable matches pattern2
    ;;
  *)
    # Code to execute if variable does not match any pattern
    ;;
esac
```
Here's an example of a case statement that prints a message based on the value of a variable:

bash

```#!/bin/bash

animal="dog"

case $animal in
  "cat")
    echo "Meow!"
    ;;
  "dog")
    echo "Woof!"
    ;;
  *)
    echo "I don't know that animal."
    ;;
esac
```
# Operators

Bash provides several operators that you can use in your scripts to perform operations on variables and values. Here are some of the most commonly used operators:

## Arithmetic Operators

Arithmetic operators allow you to perform mathematical operations on variables and values. Here are the arithmetic operators that Bash provides:

| Operator | Description         |
|----------|---------------------|
| +        | Addition            |
| -        | Subtraction         |
| *        | Multiplication      |
| /        | Division            |
| %        | Modulus (remainder) |
| *        | *	Exponentiation  |

Here's an example of using arithmetic operators to perform calculations in a Bash script:

```bash

#!/bin/bash

num1=10
num2=5

sum=$((num1 + num2))
difference=$((num1 - num2))
product=$((num1 * num2))
quotient=$((num1 / num2))
remainder=$((num1 % num2))
power=$((num1 ** 2))

```
## Comparison Operators

Comparison operators allow you to compare values and variables to see if they are equal, not equal, greater than, or less than. Here are the comparison operators that Bash provides:

| Operator | Description              |
|----------|--------------------------|
| -eq      | Equal to                 |
| -ne      | Not equal to             |
| -gt      | Greater than             |
| -ge      | Greater than or equal to |
| -lt      | Less than                |
| -le      | Less than or equal to    |
