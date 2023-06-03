# Css cascade

The cascade determine how attributes are apply to an element.

## Specificity

The more specific css declaration take precedence over less specific ones.

[Inline style](css_basics#Inline) have the highest specificity over selectors.

The order for selector is:

1. Id
2. Class
3. Type

A rule that uses more of the same selector as another one take precedence:

```css
<div class="class1 class2"></div>

.class1 {
  color: blue;
}

.class1 .class2 {   <- take precedence because 2 of the same selector
  color red;
}
```
But one higher selector take precedence over 2 lesser:

```css
<div class="class1 class2" id="id1"></div>

.id1 {              <- take precedence because id > class
  color: blue;
}

.class1 .class2 {
  color red;
}
```

### Inheritance

`Inheritance` refers to certain properties that when applied to an element,
are inherited by that element's descendants, even if not explicitly stated.

Typography properties are usually inherited: `color`, `font-size`, `font-family`

### Rule order

If after all those above rule, there is still conflicting rules to an element,
the last define selector take precedence.

```css
<div class="class1 class2"></div>

.class2 {
  color: blue;
}

.class1 {     <-- take precedence because last defined
  color red;
}
```
