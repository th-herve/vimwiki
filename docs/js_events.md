# Javascript events

There are three methods to add event listener to HTML:

- Attach to the DOM node
- On the DOM node
- In the HTML

The first method is usually the best (The two other are cover at the end).

## Best method: Attach to the DOM node

This is usually the best method.

```javascript
<button id="btn">Click Me Too</button>

const btn = document.querySelector("#btn");
btn.addEventListener("click", () => {
    alert("Hello!");
});
```
## Attach listener to a group of nodes

Use `.querySelectorAll` and then add the listener on that element. Then the
`forEach` keyword.

```javascript
const buttons = document.querySelectorAll("button");

buttons.forEach(btn => btn.addEventListener("click", () => {
    alert("Hello");
}));
```

## Named function

Regardless of the methods used, a named function can be used instead of an `arrow function`.

```javascript
function myFunction() {
    console.log("Hello");
}

btn.addEventListener("click", myFunction);
```

## Passing the event as argument

Regardless of the methods used, the event can be passed as argument in the function called.

It passes an object that references the `event` itself.
It gives access to properties and methods such as the key pressed, or the DOM node clicked...

```javascript
btn.addEventListener("click", function (e) {
    console.log(e.target);
    e.target.style.background = "blue";
});
```

### Events

| event    | description  |
|----------|--------------|
| click    |              |
| dblclick | double click |
| keydown  |              |
| keyup    |              |

[list](https://www.w3schools.com/jsref/dom_obj_event.asp)

## Other methods

### On the DOM node

```javascript
<button id="btn">Click Me</button>

const btn = document.querySelector('#btn');
btn.onclick = () => alert("Hello World");
```
>Note: can only add one event listener

### In HTML

```html
<button onclick="functionName()">Click here</button>
```

>Note: not ideal because cluttering the HTML.
