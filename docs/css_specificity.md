# Css specificity

The css specificity of a selector determine which style 
will be apply to an element if several style can apply to it.

## Calcul

The specificity of a selector statement is represented like so `0,0,0,0`

Each digit represent the number of given selector contain in the
selector statement. In order of most specificity to least:

- first digit: style attribute
- second digit: id
- third digit: class, pseudo-class, attribute
- fourth digit: element

Example:

```css
<div style="border 1px">text<div/>   1,0,0,0  --> most specificity

#my-id {...}                         0,1,0,0

.my-class {...}                      0,0,1,0

div {...}                            0,0,0,1  --> least specificity
```

More complex example:

```css
ul#nav li.active a {...}             0,1,1,3

ul#nav li.active {...}               0,1,1,2
```
Here the first selector would take precedence over the second.

First one:

- 0 style attribute
- 1 id
- 1 class, pseudo-class, attribute
- 3 elements

First one:

- 0 style attribute
- 1 id
- 1 class, pseudo-class, attribute
- 2 elements

[source](https://css-tricks.com/specifics-on-css-specificity/)
