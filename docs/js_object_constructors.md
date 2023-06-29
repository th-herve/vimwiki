# Object constructors

Object constructors provide an easier way to create several similar objects.

By convention, constructor start with a capital letter.

```javascript
function Person(name) {
    this.name = name;
    this.introduction = function () {
        console.log(`Hi my name is ${this.name}`);
    };
}
```
To create an object with a constructor, use the `new` keyword.

```javascript
const bob = new Person("Bob");
```
