# === HTML basics ===

## Basic HTML Structure

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>

    <!--import the css file-->
    <link href="test.css" rel="stylesheet">
    <meta name="viewport" content="initial-scale=1, width=device-width">

    <!--import the js file-->
    <script src="javascript.js"> </script>
  </head>

  <body class="body" id="personal-id">
    Page content goes here.
  </body>
</html>
```

## Headings

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

## Paragraphs

```html
<p>This is a paragraph.</p>
```

## Links

```html
<a href="https://example.com">Link Text</a>
```
Can have an `absolute` or `relative` path.  
Absolute: https://google.com
Relative: ./folder/file.html   `!!`prefixing the path with a `.` prevent unexpected issue




## Images

```html
<img src="./image.jpg" alt="Image Description">
```
Can use `absolute` or `relative` path.  
> `!!`It is best practice to always have an alt.

## video

```html
<video autoplay loop muted width="1280" > 
      <source src="title.mp4" type="video/mp4">
</video>
```

## Lists
ul = unordered list

ol = ordered list
```html
<ul>
  <li>List Item 1</li>
  <li>List Item 2</li>
  <li>List Item 3</li>
</ul>

<ol>
  <li>List Item 1</li>
  <li>List Item 2</li>
  <li>List Item 3</li>
</ol>
```
## Tables

```html
<table>
  <tr>
    <th>Column 1</th>
    <th>Column 2</th>
  </tr>
  <tr>
    <td>Row 1, Column 1</td>
    <td>Row 1, Column 2</td>
  </tr>
  <tr>
    <td>Row 2, Column 1</td>
    <td>Row 2, Column 2</td>
  </tr>
</table>
```

## Forms

```html
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">
  
  <label for="email">Email:</label>
  <input type="email" id="email" name="email">
  
  <input type="submit" value="Submit">
</form>
```

## modifier

```html
<p>This is <b>bold</b> <i>italic</i> <u>underline</u> </p>
```

[all the tags](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
