# Javascript promises advanced

## Promise.all()

`Promise.all()` is used when you need to wait for several
promise to finish `successfully` before doing a task.

It takes an `iterable` as argument (usually an array of promise). It
return an `array` of resolved value.
However if any of the input promises are rejected, the return value
will be the reason for the first rejection.

```javascript
function job(delay) {
    return new Promise(function(resolve) {
            setTimeout(function() {
            console.log('Resolving');
            resolve('done' + delay);
            }, delay);
    });
}

const promise = Promise.all([job(1000), job(2000), job(500)]);

promise

.then(function(data) {
        data.forEach(function(text) {
            console.log(text);
        });
});

// output:
// done 1000
// done 2000
// done 500
```

### Get result even if one promise rejected

Even if a promise is rejected, we can have the result
of the other. We can do it by attaching a `.catch()` callback 
to each promise.

```javascript
const promise = Promise.all([job(1000).catch(function() {}), job(2000).catch(function() {})]);
```

## Promise.race()

`Promise.catch()` take an iterable of promises as argument and return a new promise.
It resolve or reject as soon as one of the given promises is resolved or reject.

Useful to fetch data from several source and use the fastest. Can be use
against a timer and trigger a rejection if the promise take too long.

```javascript
function delay(time) {
    return new Promise(function(resolve) {
        setTimeout(resolve, time, 'success ' + time);
    });
}

Promise.race([delay(500), delay(100)]).then(function(data) {
    console.log(data);
});

// output
// sucess 100
```
