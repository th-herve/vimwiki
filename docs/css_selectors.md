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

Apply the same style to several element.

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

Narrow a selection by selecting element with several selector.
Simply write the selector one after the other without space to select the elements that has all those selector.

```html
<div class="my-class my-other-class">text</div>
<div class="my-class" id="my-id">other text</div>
```
```css
/* select element that has both my-class and my-other-class */
.my-class.my-other-class {
    color red;
}

.my-class#my-id {
    color: blue;
}
```
>Note: you can chain as many selector as needed, but with `type selector` you can only chain one. 
> If we want to chain a div and a p it does not work. Because it gives us `divp`

### Descendant combinator

A `descendant combinator` will only select the last element listed if it has a parent (or grandparent) selector 
that matches the previous one.

Use it by separating selector by a space. Only the `last child` element is selected.

```css
/* will select every div in the .parent container, including child, grandchild... */
.parent div {
    color: blue;
}
```
> Note: you can add has many ancestor as you want. But avoid it.

### > selector

The `>` selector is similar to the descendant combinator but only select 
the last element if it is a direct child of the previous selector.

```css
/* select every direct child div in the .parent element */
.parent > div {
    color: blue;
}

/* select every grandchild div in the .parent element and that are inside another div */
.parent > div > div {
    color: blue;
}
```
What would be selected:
```html
<main class="parent">
    <div>.parent > div</div>
    <div>
        <div>.parent > div > div</div>
    </div>
</main>
```

### + selector

The `+` selector will select the element adjacent to the first one and 
at the same level of indentation. (It's weird, just look the example)

```css
.group1 + div {...}
.group1 + div + div {...}
```
```html
<div class="group1"> Not selected </div>
<div class="group2"> selected by: .group1 + div </div>
<div class="group3"> selected by: .group1 + div + div </div>
```

### ~ selector (sibling combinator)

Select all element's sibling. Without selecting the element itself.

```css
.group1 ~ div {...}
```
```html
<div class="group1"> Not selected </div>
<div class="group2"> Selected </div>
<div class="group3"> Selected </div>
```
