# C++ constructors

A `constructor` is a special method that is automatically called when an object of the
class is created.

It has the same name as the class and no return type. They are used to initialize class attributes and do setup work.

## Default constructors

A `default constructor` takes no parameters. If the object is instantiate without specifying values,
the default constructor is called.

It is useful to ensure that a instance of the class is always initialized.

```cpp
class Sport {
private:
    std::string sport_name;
    int player;
    
public:
    // default constructor 
    Sport () {
        sport_name = "tennis";
        player = 2;
    }
};

// create a Sport object in main
int main() {
    // my_sport will have tennis as its name and 2 as player
    Sport my_sport;
};
```
## Constructor with parameters

Like functions, constructors can be declared with parameters.
It allows to instantiate object with given values.

A constructor can be overloaded so a class can have multiple constructor.


```cpp
class Sport {
private:
    std::string sport_name;
    int player;
    
public:
    // default constructor
    Sport () {
        sport_name = "tennis";
        player = 2;
    }
    
    // constructor with parameter
    Sport(std::string my_sport, player_number) {
       sport_name = my_sport; 
       player = player_number
    }
};

int main() {
    Sport basket("basket", 10);
}
```
## Constructor default parameters

Constructor's parameters can have default values. This can help reduce the number of constructor.

The above example can be reduce to:

```cpp
class Sport {
private:
    std::string sport_name;
    
public:

    // constructor with parameter
    Sport(std::string my_sport = "tennis", int player_number = 2) {
       sport_name = my_sport; 
       player = player_number;
    }
};

int main() {
    // sport_name will be "tandem" and player default to 2
    Sport tandem("tandem");
}
```
> `⚠` The compiler match arguments from left to right. So in our case, this following example is not possible:

```cpp
Sport new_sport(10);
```
> To make it possible, a constructor that take one `int` parameter must be created.

## Member initializer lists (initialize constant and more...)

The constructor example shown have been `assigning` value, not `initating` them.
This causes a problem when dealing with `const` or `reference` variables, that need to be initialized when declared.

C++ provide a way to initialize attributes with `member initalizer list`.
It is placed after the constructor parameters list. It begin with a colon `:`, it then list 
the attribute and the initial value for it.

```cpp
class Book:
private:
    const std::string title;
    const int pages;
    int price;
public:
Book() {
    // member initalizer list
    :title("it"), pages(1000) {
    // other attribute
    price = 10;
    }
};
```
They can have default value, just specify them in the parameter.

```cpp
Book::Book(std::title new_title = "title", int new_pages = 10) 
    :title(new_title), pages(new_pages) {}
```
>`⚠` Don't forget the brackets `{}` after the list.


## Define constructors outside of class

Just like methods, constructors can be defined outside of their class. 
Use the `ClassName::` namespace to indicate its class.

```cpp
House::House() {
    rooms = 5;
}
```

## Destructors

A `destructor` is another type of method that is automatically called. But this time when
an object is `destroyed` (moves out of scope or explicitly deleted).
It help clean-up the work and prevent memory leaks.

Like the constructor, it has the same name as the class and no return type.
It is preceded by a `~` and take `no parameters`.

```cpp
class Sport {
private:
    std::string sport_name;
    
public:

    // constructor with parameter
    Sport(std::string my_sport = "tennis", int player_number = 2) {
       sport_name = my_sport; 
       player = player_number;
    }

    // destructor
    ~Sport() {
        std::cout << "deleted" << sport_name;
    }
};
