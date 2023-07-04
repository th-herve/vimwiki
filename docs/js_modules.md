# Javascript modules

A module create `one` object and allows to hide some of its
properties.

It is similar to [factory functions](js_factory_functions.md) but
can't be reuse for several objects.

It uses an `IIFE` (Immediately Invoked Function Expression).
The function is wrap in parenthesis and we add another pair
of parenthesis at the end.

```javascript
const calculator = ( () => { // open parenthesis here
    const add = (a, b) => a + b;
    const sub = (a, b) => a - b;
    const mul = (a, b) => a * b;
    const div = (a, b) => a / b;
    
    return {
        add,
        sub,
        mul,
        div,
    };
}) (); // close parenthesis here, and add a pair
```
