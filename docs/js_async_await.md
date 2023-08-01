# Javascript async await

The async/await keywords are syntactic sugar for a promises.

## Async keyword

The async keyword is used to declare a asynchronous `function`.
It automatically `return a promise`.
Returning a async function is the same as resolving a promise.
While throwing an error will reject it.

It can be use before any function declaration:

```javascript
const assyncFunction = async () => {return result};

array.forEach(async item => {return result});

server.getInfo().then(async info => {return result});
```

## Await keyword

The `await` keyword can be used, on a `variable` that return a promise. 
It can only be used in a function that is declared with the `async` keyword.

It `pause` the execution of a function to wait for a value. It replace
the `.then()` method.

```javascript
async function getInfo() {
  const response = await fetch('https://api.com/v1/...');
  const info = await response.json();
  return info;
}
```

## Error handling

### try/catch

```javascript
async function getInfo() {
    try {
        const info = await server.fetchInfo();
        return info;
    } catch (error) {
        console.log(error);
    }
}
```

### .catch()

Since a async function return a promise, the `.catch()` method
can be called on it.

```javascript
assyncFunction().catch(error => console.log(error))
```
