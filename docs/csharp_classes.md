# C# classes

Classes are used to create custom types.  
A classe defines the info, and methods included in a custom type
The elements of a class are called member (field, method, properties...)

## Declaration
To declare a class : 
 - access modifier class Identifier
   {

   }
 - name of the class should be PascalCase
```C#
public class BasicClass
{
    string name;
    public int number;
}
```
To declare a new objet from that class:

```C#
BasicClass myClass = new BasicClass();
```
> **Note:** myClass here is technichaly a pointer 

# Constructor
A constructor is called each time an instance of a class is created  
Like method, it can be [overloaded](https://github.com/Adiantum-f/Cheat-sheet/blob/338899b5450530200b69b6348e73fda8c53f9b94/C%23/C%23_methods.md#L74-L94)

It initialise the fields and properties of the instance of the class. It must have the same name as the class
```C#
class Person
{  
   // field of the class
   public string name;
   
   // constructor
   public Person(string nameArgument)
   {
      // Initialize the name field with the name passed in argument when the instance is created
      name = nameArgument;
   }
}

```

Call it with the keyword `new` and the argument when creating a instance

```C#
// enter the argument of the constructor when creating a instance
Person person = new Person("Bob");
```

>**Note:** In the exemple the constructor initialize the field, when it initialises a properties, it is common to use the `this.` keyword like so `this.Properties`, while not necessary, this can be useful when the property has the same name as a parameter passed to the constructor
# Access modifiers

specify the accessibility of classes, methods, properties, fields, and other members of a program

Five in C#:
- public: can be accessed from anywhere in the program
- private: restrict access to the current class or struct
- protected: can be accessed within the containing type and its derived classes (can be accessed by inhereted class)
- internal
- protected internal

By default, classes are public  
fields, properties, and methods are private

# Field

Store a piece of data within an object  
Act like a variable, each instance can have a diffrent value  
Are tied with properties (next chapter)

A field can have modifier:
- public: access anywhere
- private: access within the class
- static: are tied to the class itself and not an instance
- virtual: can be overidden by a derived class
- ...

By default it is private

Declare a field:

    - accessModifier modifier type Name;
_
```C#
public class MyClass
{
    private int myField = 42;

    public readonly string anotherField;

    public static double staticField;

    public virtual bool virtualField;
}
```

# Properties

Control how one field can be accessed or modified  
It define two method, a getter and a setter: 
- get()
- set()

They define the comportment of the class to get and set a field

You can create a read only or write only property by ommiting one of them

In this exemple, since the field name is private, it cannot be access outside the class. But since the property is public, the field can be modified through the property
```C#
public class Person {
    // field name
    private string name;

    // properties of the field
    public string Name {
        get { return name; }
        set { name = value; }
    }
}

Person p1 = new Person();
// set the name
p1.Name = "Daniel" 
// get the name
Console.WriteLine(p1.Name)
```

### Auto-implemeneted property

Simpler syntax for simple properties without logic  
Replace the code above

```C#
public class Person
{
  public string Name
  { get; set; }

  public string Age
  { get; set; }
}
```

A property can have a access modifier

```C#
public class Person
{
  public string Name
  { private get; set; }

  public string Age
  { get; private set; }
}
```

# Static constructor

A static constructor is run once per type, not per instance  
It must be parameterless  
It is called automatically when a class is first used or an instance of the class is created

It is define with the static keyword followed by the name of the class  
    - ClassName.

```C#
public class Person {

     // properties
    public string Name { get; set; }
    public int Age { get; set; }
    


    // static constructor, is commun to all the instances of the class
    static Person() {
        static public int NumberOfLeg = 2;
    }

    // instance constructor, can differ from instance to instance
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
    
}


//ex:

p1.Name // "Sophie"
p2.Name // "Daniel"

p1.NumberOfLeg // 2
p2.NumberOfLeg // 2

```

### Static class

A whole class can be static  
It cannot be instantiated  
Its menber are accessed by the class name

Useful to have a class that provides a set of tool  
ex: a library

Math is a common static class

```C#
Math.Min(23, 97);
Console.WriteLine("Let's Go!");
```
