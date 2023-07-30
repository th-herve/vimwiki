# Javascript promises basics

## Basics

```javascript
const promise = new Promise(function(resolve, reject) {
    const truc = fetchSomething();
    
    if (truc) resolve(truc);
    
    else reject('no truc today :(');
});

promise

.then(function(data) {        // .then create a callback, trigger at the completion of the promise
    arrayOfTruc.push(data);
});

.catch(function(data) {
    arrayOfTruc.push(backupTruc)
});
```

## .then()

The `.then methods` attach a callback function that will be executed
when the promise is resolved successfully. It receive the resolved value
as argument.

An optional second function can be passed as argument to handle rejection.
It receive the reason for rejection as its argument. (It can be from an error object, promise reject, throw keyword...)

```javascript
promise.then(onFullfilled, onReject);
```

Adding a reject callback will be specific to the `then`. To have a global
error handler, use `.catch()`.

## .catch()

The `.catch()` methods attach a callback function that will be executed
when the promise is rejected.
It receive the reason for rejection as its argument.

A catch `return value` will be treated as a `resolved promise`

```javascript
promise.catch(onRecject);
```
In a promise chain, it will caught every error that happen `before` it
in the chain. It's good practice to have the last element of the chain
be a `.catch()` to ensure any error is handle.

## Promise chain

The return value of catch() and then() being a promise, it allows to chain them.

If no return value is provided, it return an `auto-resolve promises`,
using this data will get `undefined`

```javascript
var promise = job1(); // job1 return a promise

promise

.then(function(data1) {
    console.log('data1', data1);
    return job2();
})

.then(function(data2) {
    console.log('data2', data2);
    return 'Hello world';
})

.catch(function(data) {     
    console.log('error');
});

.then(function(data3) {
    console.log('data3', data3);
});

.catch(function(data) {
    console.log('error');
});

// adding a .then on this then would get an undefined data

function job1() {
    return new Promise(function(resolve, reject) {
        setTimeout(function() {
            resolve('result of job 1');
        }, 1000);
    });
}

function job2() {
    return new Promise(function(resolve, reject) {
        setTimeout(function() {
            resolve('result of job 2');
        }, 1000);
    });
}

// output:
data1 result of job 1
data2 result of job 2
data3 Hello world
```

>Note that the promise and the three .then are the same line of code split


[Promises error to avoid](https://www.codingame.com/playgrounds/347/javascript-promises-mastering-the-asynchronous/traps-of-promises)
