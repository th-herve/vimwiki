# C# References

In C#, classes and interface are `reference` types. They store a reference to their data, not the date itself (similar to pointers).

Multiple variables can reference the same object and any changes made to the object though one variable will be reflected in all the other variables that reference the same object

>**Note:** an object of type Object, string or dynamic is also a reference type.

An object can be referenced by any type it inherited from or by any interfaces it implements.

```C#
class Vehicule : IMachine {}
class Car : Vehicule {}
class SUV : Car {}

// 4 rerferences to the same instance
SUV Mercedes = new SUV();
Car MercedesAsCar = Mercedes;
Vehicule MercedesAsVehicule = Mercedes;
IMachine MercedesAsMachine = Mercedes;
```

Depending on the reference type, the same object can have different functionalities.

## Upcasting and Downcasting

Upcasting refers to converting an object of a derived class to its base class, while downcasting refers to converting an object of a base class to its derived class.

```C#
class Car {}
class SUV {}

SUV Mercedes = new SUV();
Car MercedesAsCar = Mercedes; // upcasting

Car Clio = new Car;
SUV ClioAsSuv = (SUV)Clio; // downcasting
```

>**Note:** downcasting can result in error.

# Null reference

An undefined reference is either **null** or **unassigned**. No operation can be performed on an **unassigned** reference but it can be done with on **null** one (Kinda).

```C#
Car Fiat; // unassigned

Car Bmw = null; // null 
```
