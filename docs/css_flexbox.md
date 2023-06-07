# Css Flexbox


## Flex containers and flex items

`Flexbox` is more that a single property, it is a whole toolbox.
Some of its property belong on `flex containers` and other on `flex items`.

A `flex container` is an element that has the `display: flex;` on it.

>Note: a element can be both a flex container and items

## Flex items

The `flex` property apply to an `flex item`.
It affect how flex items size themselves within their container.

It is a shorthand for the three property:

1. flex-grow: how much of the available space, the element will take by growing
2. flex-shrink: rate at which the element is shrinking. (0 = does not shrink)
3. flex-basis: base size in px of the element. It will not shrink below that point.

[More on the shorthand aspect](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)

```css
.item {
    flex: 1;
}
```
A             B              C
+---------+   +----------+   +----------+
¦         ¦   ¦          ¦   ¦          ¦
¦ ◼  ◼  ◼ ¦   ¦ ▀▀ ▀▀ ▀▀ ¦   ¦▀▀ ▀▀ ▀▀▀▀¦
¦         ¦   ¦          ¦   ¦          ¦
¦         ¦   ¦          ¦   ¦          ¦
+---------+   +----------+   +----------+
  no flex       equal flex     unequal flex   

- A: `no flex` property on the items
- B: `flex: 1;` on each items
- C: `flex: 1;` on the first two items, `flex: 2;` on the last


## Properties

Some apply to containers and other to items.

### Horizontal alignments

The `justify-content` attributes apply to the `container`.
It defines the horizontal alignments of its items.

+---------+   +---------+   +---------+
¦ ◼◼◼     ¦   ¦   ◼◼◼   ¦   ¦     ◼◼◼ ¦ 
+---------+   +---------+   +---------+ 
 Flex-start      center       flex-end

+---------+      +---------+
¦ ◼  ◼  ◼ ¦      ¦◼   ◼   ◼¦
+---------+      +---------+
space-around     space-between

### Vertical alignments

The `align-items` attributes apply to the `container`.
It defines the vertical alignments of its items.
```markdown
+---------+   +---------+   +---------+   +---------+
¦         ¦   ¦   ◼     ¦   ¦         ¦   ¦ █       ¦ 
¦         ¦   ¦   ◼◼◼   ¦   ¦   ◼     ¦   ¦ █       ¦ 
¦   ◼     ¦   ¦         ¦   ¦   ◼◼◼   ¦   ¦ █  █  █ ¦ 
¦   ◼◼◼   ¦   ¦         ¦   ¦         ¦   ¦ █  █  █ ¦ 
+---------+   +---------+   +---------+   +---------+ 
    end          start         center      strech
```

### Wrapping items

Let the overvlow item wrap and create a grid with the `flex-wrap` property.
It apply to the `container`.

+---------+        +---------+
¦ ◼ ◼ ◼ ◼ ¦◼ ◼ ◼   ¦ ◼ ◼ ◼ ◼ ¦
¦         ¦        ¦  ◼ ◼ ◼  ¦
¦         ¦        ¦         ¦
¦         ¦        ¦         ¦
+---------+        +---------+
  nowrap               wrap 
  
### Flex direction

The `flex-direction` attributes apply to the `container`.
It refers wheter its items are render horizontally or vertically.

+---------+   +---------+
¦         ¦   ¦    ◼    ¦
¦ ◼ ◼ ◼ ◼ ¦   ¦    ◼    ¦
¦         ¦   ¦    ◼    ¦
¦         ¦   ¦    ◼    ¦
+---------+   +---------+
    row          column

>Note: When rotating the direction of a container, the attributes `justify-content` and `align-items`
> are inverted [More on this.](https://internetingishard.netlify.app/html-and-css/flexbox/index.html#alignment-considerations)

## Grouping flex items

Flex containers only know the position of elements one level below.
It means you can group flex items by wrapping them inside an extra div.

A                B
+---------+      +---------+
¦◼   ◼   ◼¦      ¦◼     ◼ ◼¦
+---------+      +---------+
No grouping      Grouped items

In example B, the two items on the right are group in a common div.
The flex container treat this div as a single item and does not apply to the items inside.


[source](https://internetingishard.netlify.app/html-and-css/flexbox/index.html)
[source2](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)
[source3](https://www.theodinproject.com/lessons/foundations-growing-and-shrinking)
