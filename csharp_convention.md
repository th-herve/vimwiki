# C# Conventions

# Naming conventions:

- class names and method/function names : PascalCase

```C#
public class MyClass
{
    public void MyMethod()
    {
        // Code here
    }
}
```

- local variables, parameters, method arguments : camelCase

```C#
public void DoSomething(int myParameter)
{
    string myVariable = "Hello";
    // Code here
}
```
## summary

| type               | format              | exemple        |
|--------------------|---------------------|----------------|
| function           | PacalCase           | MyFunction     |
| function parameter | camelCase           | myParameter    |
| constants          | UPPERCASE_SnakeCase | CONSTANT_NAME  |
| properties         | PacalCase           | PropertiesName |
| event              | PacalCase           | EventName      |
| fields             | camelCase           | EventName      |

# Indentation:

```c#
public void MyMethod()
{
    if (someCondition)
    {
        // Code inside braces is indented four spaces
        // ...
    }
    else
    {
        // ...
    }
}
```

# Comments:

```c#
// Single-line comments for short comments
public void MyMethod()
{
    // This is a short comment
    // ...
}

/// XML documentation comments for documenting classes, methods, and parameters
/// <summary>
/// This is a summary of the class or method
/// </summary>
public class MyClass
{
    /// <summary>
    /// This is a summary of the method
    /// </summary>
    /// <param name="myParameter">This is a summary of the parameter</param>
    public void MyMethod(int myParameter)
    {
        // ...
    }
}

```

# Braces:

```C#
public void MyMethod()
{
    if (someCondition)
    {
        // Opening brace on the same line as the statement or declaration
        // Closing brace on its own line
        // ...
    }
    else
    {
        // ...
    }
}

```

# Line length:

- Keep lines of code shorter than 80 characters.

```C#
public void MyMethod()
{
    // Keep lines shorter than 80 characters
    string myString = "This is a long string that should be broken up into multiple lines " +
                      "to improve readability.";
}

```
# Formatting:
- Use a consistent and readable formatting style.
- Use whitespace to separate logical blocks of code.
- Use vertical whitespace to improve readability.

```C#
public void MyMethod()
{
    // Use whitespace to separate logical blocks of code
    if (someCondition)
    {
        // ...
    }

    // Use vertical whitespace to improve readability
    // ...
    // ...
}

```

# Exception handling:

- Use try-catch blocks to handle exceptions.
- Throw exceptions with meaningful messages.

```C#
public void MyMethod()
{
    try
    {
        // Code that might throw an exception
    }
    catch (Exception ex)
    {
        // Handle the exception
        throw new Exception("An error occurred: " + ex.Message);
    }
}

```

# Enums:

- Use PascalCase for enum names.
- Use singular names for enums (e.g. `Color`, not `Colors`).

```C#
// Enum names in PascalCase
public enum Color
{
    Red,
    Green,
    Blue
}

```

## Boolean values:

- Use descriptive boolean variable names (e.g. `isReady`, `hasValue`, not `flag`, `boolValue`).

```C#
public void MyMethod()
{
    bool isReady = true;
    bool hasValue = false;

    // Use descriptive boolean variable names
    if (isReady)
    {
        // ...
    }

    if (!hasValue)
    {
        // ...
    }
}

```

## Constants:

- Use all uppercase for constants.
- Use descriptive names for constants.

```C#
// Constants in all uppercase
public const int MAX_VALUE = 100;

// Use descriptive names for constants
public const string ERROR_MESSAGE = "An error occurred.";

```
