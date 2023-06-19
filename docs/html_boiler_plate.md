# html boiler plate

```html

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My First Webpage</title>
    
    <link href="style.css" rel="stylesheet">
    <script src="script.js" defer></script>
  </head>

  <body>
  </body>
</html>

```

## The DOCTYPE

Tell the browser the version of html to render the document.

For html5:

- `<DOCTYPE html>`

## Html element

Root element.

```html
<html lang="en">
</html>
```

The `lang` attribute specify the language and improve accessibility.

## Head element

The `<head>` element store important meta-information about the page, and requirement to render correctly in the browser.

>`` Do not put element that display content.

### Charset meta element

Always include the charset encoding of the webpage.  
It ensures that the page display special symbols and character correctly.

>  `<meta charset="uft-8">`

### Title element

Title displayed in the browser tab. Should always be included.  
If not specify, the name of the file is displayed. (ex: index.html)

> `<title>webpage tilte</title>`

## Body element

Element where the content displayed to the user is specify.


