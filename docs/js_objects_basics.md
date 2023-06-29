# Javascript objects bascics

## Create an object

```js
let user = {
    name: "John",
    age: 30,
    description: function () {
        console.log(`name: ${this.name} age: ${this.age}`);
    },
    name() {
        console.log(`my name is ${name}`);
    },
};
```
>Note: there is 2 way to add a function in an object.

>Note: this method of creating an object is known as `object literal`, 
> another method is the use a `constructors`(see below).

## Object constructors

Object constructors provide an easier way to create several similar objects.

By convention, constructor start with a capital letter.

```js
function Person(name) {
    this.name = name;
    this.introduction = function () {
        console.log(`Hi my name is ${this.name}`);
    };
}
```
To create an object with a constructor, use the `new` keyword.

```js
const bob = new Person("Bob");
```

## Access value

```js
user.name;
user.name();

// or

user["name"];
```

## Remove value

```js
delete user.age;
```

## Loop over an object

Use `for...in` loop.

```js
for (let key in object) {
    // code
}
```

## Test property existence

```js
if (keyName in user) {...}

// or

if (user.keyName == undefined) {...}
``` 
