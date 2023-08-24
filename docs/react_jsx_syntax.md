# Jsx syntax

Jsx is a javascript extension that allows to write html in javascript.

>Note: it is independent from react

## Rules

Their is a few rules to follow when writing html in jsx that differ from
normal html.

You can use a html to jsx [converter](https://transform.tools/html-to-jsx) to convert.

1. It must return a single root element

  If you want to return multiple tag, wrap everything in a div or with
  a `fragment`: `<> </>`.  A fragment won't leave trace in the final html.

  ```javascript
  function Component() {
    return (
      <>
        <h1>text</h1>
        <p>hello there</p>
      </>
    );
  }
  ```
2. Close all tags
  
  All tag must be closed, even self closing one.
  <img> become <img />.

3. camelCase most thing

  Attribute written in kebab-case must be converted in camelCase.
  stroke-width become strokeWidth.

  The keyword `class` become `className`.

## Use javascript in jsx

Use curly braces `{}` to inject javascript variable, function... inside
html.

### Variable

```javascript
function Component() {
  const name = "Bob";
  return (
    <h1>Hello {name}</h1>   // pass the name
  )
}
```

### Function

```javascript
function formatDate(date) {
  // format date code here
}
function Component() {
  return (
    <h1>We are the {formatDate(today)}</h1>   // pass the name
  )
}
```
