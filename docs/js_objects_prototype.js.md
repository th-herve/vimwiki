# Javascript objects prototype

All javascript object have a `prototype`. It is also an `object` that
the original object `inherits from`. The original object has access
to all of the prototype's method and properties.

Using a `prototype` can `save space`. It allows to declare common function
and properties to several object without defining it for each one.

## Defining a function in a prototype

```javascript
myObject.prototype.myFunction = function() {
    console.log("Hello");
}

myObject.myFunction();
```

## Accessing an object's prototype

Use `Object.getPrototypeOf(myObject)`.
Other method exits but are not recommended: 

- `myObject.__proto__`
- `myObject[[Prototype]]`

```javascript
Object.getPrototypeOf(myObject) === 

myObject.__proto__ ===
myObject[[Prototype]] ===
```
## Setting an object's prototype

Use `Object.setPrototypeOf(objectOne.prototype, objectTwo.prototype)`.
objectTwo.prototype become the prototype of objectOne.prototype.

`!!`Use it `before` creating objects.

```javascript

// create a Animal constructor (by default its prototype is Object.prototype)
function Animal(name) {
    this.name = name;
}

// create a function to Animal, and create the Animal.prototype
Animal.prototype.walk = function() {
    console.log("is walking");
}
// Note: Animal.prototype, since it is an object, has Object.prototype as its
// proto. So Animal still has access to this proto

// create a Cat constructor (by default its prototype is Object.prototype)
function Cat(name) {
    this.name = name;
}

// Set the Cat proto to be the same as Animal (create a copy)
Object.setPrototypeOf(Cat.prototype, Animal.prototype);
```

### Prototypal inheritance

When you attempt to access a property or method of an object, 
JavaScript will first search on the object itself, and if it is not found, 
it will search the object’s Prototype. If after consulting both the object and its Prototype 
still no match is found, JavaScript will check the prototype of the linked object, 
and continue searching until the end of the prototype chain is reached.

At the end of the prototype chain is `Object.prototype`. All objects inherit the properties and methods of Object. 
Any attempt to search beyond the end of the chain results in null.

>Note: by default, an object's prototype is `Object.prototype`
