# Javascript objects basiccs

## Create an object

```javascript
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
> another method is the use of a [constructor](js_object_constructors.md).
> Prefer using a constructor


## Access value

```javascript
user.name;
user.name();

// or

user["name"];
```

## Remove value

```javascript
delete user.age;
```

## Loop over an object

Use `for...in` loop.

```javascript
for (let key in object) {
    // code
}
```

## Test property existence

```javascript
if (keyName in user) {...}

// or

if (user.keyName == undefined) {...}
``` 
