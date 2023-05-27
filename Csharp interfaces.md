# === C# Interfaces ===

An interface defines a set of properties, methods and events that a class can implement. It specifies what a class must provides, if it implements the interface. 

It does not provide any implementation of its element.

It is defined with the keyword `interface`, followed by its name, in Pascalcase and starting with I

```C#
interface IAnimal {
    void Eat();
    int Legs { get; }
}
```

An interface can contain a declaration of:

- Methods
- properties
- Indexers
- Events

> **Note:** can't contain field

# implementation

To implement an interface in a class, it must: 

- follow the class declaration after `:` 
- implement the elements of the interface inside the class

```C#
class Dog : IAnimal 
{
    public int Legs { get; }

    public void Eat()
    {
        Console.WriteLine("The dog is eating");
    }
}
```
