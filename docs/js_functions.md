# Javascript functions

## Declare function

Use the `function` keyword.

function [functionName]([parameter]) {
    declaration;
}

```js
function myFunction() {
    console.log("hello");
}
```

## Anonymous functions

An `anonymous funciton` doesn't have a name.

```js
(function () {
    console.log("hello");
});
```
It is mostly use when a function expect another function as parameter.

```js
textBox.addEventListener("keydown", function (event) {
    console.log(`you pressed "${event.key}"`);
});
```

## Arrow functions

An alternative to anonymous functions are `arrow functions`.

Instead of `function (event)`, you use `(event) =>`.

```js
textBox.addEventListener("keydown", (event) => {
    console.log(`you pressed "${event.key}"`);
    });
```
>Note: if there is only one parameter, you can omit the parenthesis`()`
> `event =>`
