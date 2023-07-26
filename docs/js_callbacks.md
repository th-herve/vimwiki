# Javascript callbacks

A callback is a function that is passed as argument to another
function, and is executed after the completion of that function.

```javascript
function doAsyncStuff(callbackFunction) {
    setTimeout(function() {
    console.log("Async operation is done");
    callbackFunction();
    }, 1000);
}

function onComplete() {
    console.log("Callback function executed");
}

// usage
doAsyncStuff(onComplete);
```

## Creating 
