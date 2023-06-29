# Javascript functions

## Declare function

Use the `function` keyword.

function [functionName]([parameter]) {
    declaration;
}

```javascript
function myFunction() {
    console.log("hello");
}
```

## Anonymous functions

An `anonymous funciton` doesn't have a name.

```javascript
(function () {
    console.log("hello");
});
```
It is mostly use when a function expect another function as parameter.

```javascript
textBox.addEventListener("keydown", function (event) {
    console.log(`you pressed "${event.key}"`);
});
```

## Arrow functions

An alternative to anonymous functions are `arrow functions`.

Instead of `function (event)`, you use `(event) =>`.

```javascript
textBox.addEventListener("keydown", (event) => {
    console.log(`you pressed "${event.key}"`);
    });
```
>Note: if there is only one parameter, you can omit the parenthesis`()`
> `event =>`
