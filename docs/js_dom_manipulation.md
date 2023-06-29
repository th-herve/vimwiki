# Javascript DOM manipulation

## Selecting a Node

You can use `css style` selectors or `relational` selectors.

```html
<div id="container">
  <div class="display"></div>
</div>
```
To select the div display:

css style:

- div.display
- .display
- #container > .display
- div#container > div.display

Relational:

- `firsElementChild`
- `lastElementChild`

```javascript
const container = document.querySelector('#container');

const x = container.firsElementChild

const y = document.querySelector('.controls');
```

## DOM methods

Each nodes of the DOM are object with properties and methods that allow web page manipulation.

### Query selectors

| methods                              | description                                      | example |
|--------------------------------------|--------------------------------------------------|---------|
| document.querySelector(selector)     | return reference to the first match              |         |
| document.querySelectorAll(selectors) | return `nodelist` with references to all matches |         |

>Note: the return value of `.querySelectorAll` is `not` an array, it is a `nodelist`.
> Some array methods don't apply to it, unless converted to an array with `Array.from()` for example.

### Element creation

document.createElement(tagName, [option])

```javascript
const div = document.createElement('div');
```
>Note: it only creates the element, it does not insert it in the DOM.

### Append elements

- parentNode.appendChild(childNode)
- parentNode.insertBefore(newNode, referenceNode): insert newNode before referenceNode.

### Remove elements

- parentNode.removeChild(child)

### Altering elements

You can use a reference to an element to alter its properties.

#### Adding inline style

```javascript
// create a reference
const div = document.createElement('div');

div.style.color = 'blue';

div.style.cssText = 'color: blue; background: white;';

div.setAttribute('style', 'color: blue; background: white;');
```

>Note: for kebab-cased css, you need to modify the notation:
    > div.style.~~background-color~~ // does not work use one of these:
    > div.style.backgroundColor
    > div.style['background-color']
    > div.style.cssText = "background-color: white;"

#### Adding attributes

Add a `class` or `id`...

setAttribute(attributesType, attributesName);

If the `attributesName` provided does not exitst, it create it.

```javascript
div.setAttribute('id', 'theDiv');

div.getAttribute('id'); // will return 'theDiv'

div.removeAttribute('id');
```
With `classes`:

```javascript
div.classList.add('new');

div.classList.remove('new');

div.classList.toggle('active');
```
> `!!` There is no dot when adding a class, it is `("className")` not (".className")
 
>Note: it is better to use `.toggle` rather than add or remove.

##### Adding text content

```javascript
div.textContent = "Hello, World!";
```

##### Adding HTML content

```javascript
div.innerHTML = "<span>Hello, World!</span>";
```
>Note: `textContent` should be prefer because less prone to javascript injection. 


