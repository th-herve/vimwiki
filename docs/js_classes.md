# Javascript Classes

```javascript
// create class
class User {

    // constructor
    constructor(name) {
        this.name = name;
    }
    
    // method 
    sayName() {
        console.log(this.name)
    }
}

// create an instance
let user = new User("Bob");
user.name       // Bob
user.sayName() //Bob
```

## Getters/setters

Getter and setter can be implemented with the `get` and `set` keywords.

```javascript
class User {
    constructor(name) {
    
        // call the setter
        this.name = name;
    }
    
    // getter
    get name() {
    return this._name;
    }
    
    // setter
    set name(value) {
        if (value.length < 4) {
            alert("Too short");
            return;
        }
        this._name = value;
    }
}

let user = new User("Bob");
alert(user.name); // Bob 
```
>Note: `this.name` call the setter, then the setter
> create the variable `_name`

## Class properties

The `class fields` syntax allows to add properties.

They are usually use to set default value before the constructor.
They can also make the class more readable by declaring the property
up-front outside the constructor.

```javascript
class User {
    // default value with property
    age = 18;
    // declaring it for clarity
    height;
    
    constructor(age, height) {
        // setting the value
        this.age = age;
        this.height = height;
    }
}

let  user = new User();
alert(user.name); // Bob
```
## Inheritance

Use the `extends` keyword to create a class as a child of
another constructor (either a class or a function).

You then call the parent class constructor with the `super` keyword.
The keyword can also be use to call the parent methods.

```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }
    
    speak() {
        alert(`this.name "make noise"`);
    }
}

class Dog extends Animal {
    constructor(name) {
        // call parent constructor
        super(name);
    }
    
    speak() {
        // call the parent speak method
        super.speak();
        alert("bark too")
    }
}
```
