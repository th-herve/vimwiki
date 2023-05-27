# === C# Methods ===

# Declaration

- Methods are declared inside a class

``` C#
access_modifier return_type MethodName(parameter_list)
{
    // method body
}
```
- Access modifier: 
    - public 
    - private

``` C#
public string MyMethod(int x, string test)
{
    // method body
}
```

# Expression bodied methods

- Shorter method declaration if it's only one expression
- accesModifier type Name(parameter) => expression;

```C#
static int Add(int x, int y)
{
  return x + y;
}

static void PrintUpper(string str)
{
  Console.WriteLine(str.ToUpper());
}

// The same methods written in expression-body form.
static int Add(int x, int y) => x + y;

static void PrintUpper(string str) => Console.WriteLine(str.ToUpper());
```

# Lambda expression

- Concise anonymous function
- Often use in a parameter of other function

```C#
parameter_list => expression
```
Here a lambda expression is past into the .Exists method as second parameter.  
This method call the lambda exp for each number n in the array and return true if any of those are equal to 10.

```C#
Array.Exists(numbers, (int n) => {
  return n == 10;
});
```

### shorter lambda

- the type declaration can by removed if it can be inferred (here from the array numbers)
- the parentheses can be removed if there is only one parameter

```C#
Array.Exists(numbers, n => {
  return n == 10;
});
```

# Method overloading

- Having multiple method name but with different parameter 
- The compiler determine wich one to use given the number and types of arguments passed

```C#
public int Add(int x, int y)
{
    return x + y;
}

public double Add(double x, double y)
{
    return x + y;
}

public int Add(int x)
{
    return x + x;
}
```

Alternatively, this below would set a "default" value for y of 2 if only one argument is specified

```C#
public int Add(int x, int y = 2)
{
    return x + y;
}
```

# out parameter

- allow to return multiple value
- out type variableName

```C#
public bool Divide(int dividend, int divisor, out int quotient, out int remainder)
{
    quotient = dividend / divisor;
    remainder = dividend % divisor;
    bool divided = true;
    return divided; 
}
```


