# Javascript factory functions

A factory function can replace a object constructors.
It sets up the new object and return it.

They should be preferred to constructors because they are less
prone to errors.

Use `camelCase` for the name.

```javascript
// factory functions
const personFactory = (name, age) => {
    const sayHello = () => console.log("hello");
    return { name, age, sayHello };
};

// object creation
const jeff = personFactory("jeff", 27);

// accessing object properties
jeff.sayHello();
console.log(jeff.name);
```

>Note: factory functions do not utilize [prototype](js_objects_prototype),
> which come at a performance penalty.

## Object shorthand

The `return` value of the factory function uses an `object shorthand`.
It allow to simplify the notation of the object.

```javascript
return { name, age, sayHello };

// equivalent
return { name: name, age: age, sayHello: sayHello };
```
>Note: the variable used must have the same name as the object property.

## Private and public properties

With the concept of [closure](js_closure.md), we can define public and
private properties and methods for the object.

Everything that is return is gonna be public. The other properties
will be private and not accessible outside the factory function.

But the public property will have access to the private one.

```javascript
// factory functions
const exampleFactory = () => {
    const publicVariable = "Im public";
    const privateVariable = "Im private";
    
    const publicMethod = () => console.log("public");
    const privateMethod = () => console.log("private");
    
    return { publicVariable, publicMethod }; // all return element are public
};

// object creation
const example = exampleFactory();

// accessing object properties
console.log(example.publicVariable;) // Im public
console.log(example.privateVariable) // Undefined
}
```

## Inheritance

Factory function does not provide inheritance by default.

There several way to implement it:

With `destructuring assignment`, you can chose property to inherit separately.
With `Object.assign()`, you can take all the property.


```javascript
const person = (name) => {
  const sayName = () => console.log(`my name is ${name}`);
  const sayHello = () => console.log("hello");
  return { sayName };
}

// destructuring assignment
const nerd = (name) {
  // destructuring assignment, only take the property sayName;
  const {sayName} = person(name); // inherit the sayName methods
  const nerdFunction = () => console.log("nerd stuff");
  return { sayName, nerdFunction }
}

// object.assign()
const sportif = (name) {
  const prototype = person(name);
  const sportfunction = () => console.log("sport stuff")
  // using Object.assign to return all the person prop + sportFunction
  return Object.assign({}, prototype, { sportFunction });
}

const jeff = Nerd("jeff");
jeff.sayName(); // my name is jeff
```
