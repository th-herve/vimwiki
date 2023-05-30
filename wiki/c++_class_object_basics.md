# C++ classes and objects basics

## Classes

Use the `class` keyword to create one, end its definition with a semicolon `;`

```cpp
class Dog {
    // class
};
```
> ` ` Don't forget the semicolon at the end 

The element of a class are called `class members`, there are two types:

- `Attributes`: contain information about an object of the class.
- `Methods`: function that belong to the class.

```cpp
class Dog {
public:
    std::string name;
    int age;
    
    void bark() {
        std::cout << name << "is barking\n";
    }
};
```
For larger projects, it’s recommended to split up the class definition in a header and a .cpp file.
Doing so requires class methods to be defined outside of the class definition. 
In this scenario, use the `ClassName::` namespace to indicate that the function belongs to that class.

```cpp
void Dog::bark() {
    std::cout << name << "is barking\n";
}
```

## Objects

Create an instance of a class or `object` 

```cpp
Dog mydog;
```

Use the `.` to access and modify its attributes or call its methods

```cpp
mydog.name = "Medor"

mydog.bark();
```
