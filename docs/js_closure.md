# Javascript closure

The concept of `public` and `private` properties does not exist in 
javascript. But it can be implemented with the concept of `closure`.

It resolve around the fact that a function retain its scope even
if it's passed around and called outside of that scope.

```javascript
// factory function
const myVariable = () => {
    let name = "Bob";
    return () => {
        console.log(name);
    };
};

// variable is a closure
const variable = myVariable;

variable.name; // error, out of scope
variable(); // log Bob
```
In the example, the variable name is private, and the function that
log the name is public.
