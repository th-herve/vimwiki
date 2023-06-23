# Css selectors

## Basic syntax

```css
selector {
    property: value;
}
```

## Selector

### Universal selector

Select everything in the document.
Use the asterisk `*`

```css
* {
    color: blue;
}
```
### Type selector

Select an element (div, p...).

```css
div {
    color: white;
}
```

### Class selectors

Use the `.` dot

```css
.my-class {
    color: red;
}
```
You can give several class to an element in html:

```html
<div class="class-1 class-2">text </div>
```

### Id selectors

Select with `#`

```css
#title {
    background-color: green;
}
```
> Note: Id tend to be overuse by beginner. Most of the time a class do the trick.

## Select several selector

### Grouping selector

If two distinct groups of elements share some style.
Join them with a coma separated list.

You can still add unique declaration afterward.

```css
.my-class,
.my-other-class {
    color: white;
    font-size: 24px;
}

.my-class {
    backgroud-color: blue;
}

.my-other-class {
    background-color: green;
}
```
### Chaining selectors

Sometimes, Html element have several selector, with some common with others, like in the example below.

```html
<div class="my-class my-other-class">text</div>
<div class="my-class" id="my-id">other text</div>
```
If both class `my-class` have some common style, but we want to add specific ones for each element,
we can narrow the selection by using `chaining selectors`.

Simply write the selector one after the other without space.

```css
.my-class.my-other-class {
    color red;
}

.my-class#my-id {
    color: blue;
}
```
It select the element that has both selectors.

It work with all selector, but with `type selector` you can only chain one. If we want to 
chain a div and a p it does not work. Because it gives us `divp`

### Descendant combinator

`Combinators` take into consideration `relationship` between selector.

A `descendant combinator` will only select the last element listed if it has a parent selector 
that matches the previous one.

Use one by separating selector by a space. Only the `last child` element is selected.

```css
.parent .child {
    color: blue;
}
```
> Note: you can add has many ancestor as you want. But avoid it.

