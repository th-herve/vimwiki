# C# inheritance

Inheriance, is the mechanism that allow a class to take properties and behavior from another:

- The `Derived Class` or `Subclass` (child): is the class that inherit from another
- The `Base class` or `Superclass` (parent): is the class it inherited from

Use the symbol `:` to indicate inheritance

```C# 
class Animal
{
    public void Eat()
    {
        Console.WriteLIne("Is eating");
    }
}

class Dog : Animal
{
    // the dog inherit the method Eat from Animal
    string name;
}
```

# C# protected keyword

The `protected` keyword is an access modifier that can apply to fields, methods and properties of a class.

The element `protected` can only be accessed by the class itself or the derived class that inherit from it.

```C#
public class Plant
{
    protected bool Photosynthesising = true;
}

// Tree can access the bool in Plant
public class Tree : Plant
{

}
```

# C# Polymorphism: override/virtual keywords

A derived class (child) can modify the methods of the base class if the methods have these keywords:

- `virtual`: in the base class, the element can be modified
- `override`: in the derived class, the element is modified

```C#
public class Plant
{
    public virtual void growing;
    {
        size += 10;
    }
}

public class Tree : Plant
{
    public virtual void growing;
    {
        size += 200;
    }
}
```
>**Note:** the keyword `new` can be use in simmilar case of  `override` but behave differently

## C# Abstract keyword

The `abstract` keyword can be used with classes, methods, properties, indexers and event  
It specifies that implementation of these elements are missing in the class, they must be implemented in a class that inherit from the abstract class

If at least one element of the class is marked `abstract`, the class itself must be marked too  
The implementation of an `abstract` in a derived class must be marked `override`

```C#
abstract class Plant
{
    public abstract void Color();
}

class Tree : Plant
{
    public override void Color()
    {
        Console.WriteLine("The tree is green");
    }
}
```

> **Note:** the difference with an interface, is that an abstract class can provide implementation of some elements

# C# new vs override

The keywords `new` and `override` can both be used to modify a method from the base class in the derived class, but they behave differently and give different output

The `override` method in the derived class replace completely the method from the base class (no matter the reference)

```C#
class Plant
{
    public virtual void Size()
    {
        Console.WriteLine("The plant is small");
    }
}

class Tree : Plant
{
    public override void Size()
    {
        Console.WriteLine("The tree is big");
    }
}

// same instance with 2 references (2 pointers to the same location)
Tree oak = new Tree();
Plant oakAsPlant = oak;

// same output
oak.Size();  // "The plant is big"
oakAsPlant.Size() // "The plant is big"
```

The `new` method on the other hand, specify that a new method is created in the derived class with the same name as in the base class. It does *not* replace it.  
The base class method can still be called if the instance is referenced with the base class

In the exemple, the output of the Size method change if the keyword new or override is used

```C#
class Plant
{
    public virtual void Size()
    {
        Console.WriteLine("The plant is small");
    }
}

class Tree : Plant
{
    // new keyword is used
    public new void Size()
    {
        Console.WriteLine("The tree is big");
    }
}

// same instance with 2 references (2 pointers to the same location)
Tree oak = new Tree();
Plant oakAsPlant = oak;

// different output
oak.Size(); // "The plant is big"
oakAsPlant.Size() // "The plant is small"
```
