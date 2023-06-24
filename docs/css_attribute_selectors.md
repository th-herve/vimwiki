# Css attribute selector

Select element by their attributes or attributes values.
Use with the bracket `[]`

It has the same specificity as classes 0,0,1,0.

- `[attribute]` select anything that has the attribute, value does not matter.
- `[attribute="value"]` select element with the attribute and the given value

Example

```css
[src] {...}

img[src] {...}

img[src="img.jpg"] {...}
```

For more complex slection you can use these:

- `[attribute^="values"]` match attribute that start with values
- `[attribute$="values"]` match attribute that end with values
- `[attribute*="values"]` match attribute contain values anywhere inside

>Note: they also work with classes, like so: `[class^="cla"]`

Example:

```css
[class^"aus"] {
  /* 
    select:
      class="australia"
      class="austria"
      ...
  */
}

[src$=".jpg"] {...}

[src*="ill"] {
  /* 
    select:
      src="bill.jpg"
      src="silly.jpg"
      src="ill.jpg"
      ...
  */
}
```

[More on it](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)
