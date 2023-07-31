# Javascript fetch

`Fetch()` provide an easy way to `retrieve or push` data asynchronously across
the web.

## Basics

The simplest fetch take one argument, `an url`, and return a 
`promise` that resolves with a [response object](js_response_object.md).

This response object contain the entire `HTTP response`.

`.json()` is used to extract the json content from the response. It
also return a promise, that resolve with the the content of the response body as json.

```javascript
fetch('https://url.com/some/api')
  .then(function(response) {
    // handle success response
    return response.json();
  })
  .then(function(json) {
    console.log(json);
  }
  .catch(function(error){
    // handle error
  })
```

## Request options

The fetch() can also take a second argument, an `init object`
used to passed options.

[Options list](https://developer.mozilla.org/en-US/docs/Web/API/fetch)

```javascript
fetch('https://url.com/some/api', {
  method: "POST",
  mode: "cors",
  cache: "no-cache",
  ...
});

```
