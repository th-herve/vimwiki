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

```markdown
A             B              C
+---------+   +----------+   +----------+
¦         ¦   ¦          ¦   ¦          ¦
¦ ◼  ◼  ◼ ¦   ¦ ▀▀ ▀▀ ▀▀ ¦   ¦▀▀ ▀▀ ▀▀▀▀¦
¦         ¦   ¦          ¦   ¦          ¦
¦         ¦   ¦          ¦   ¦          ¦
+---------+   +----------+   +----------+
  no flex       equal flex     unequal flex   
```
- A: `no flex` property on the items
- B: `flex: 1;` on each items
- C: `flex: 1;` on the first two items, `flex: 2;` on the last

## Main-axis and Cross-axis

The flexbox operate on two axis.
 
- `main` axis or `flex-direction: row;`
- `cross` axis or `flex-direction: column;`

By default, the `main axis` is horizontal.
The `cross axis` is vertical.

They are inverted if the `flex-direction` property is set to `vertical` on the `container`.

```markdown
---main--->       ---cross--->     
+---------+  |    +---------+  |
¦         ¦  |    ¦         ¦  |
¦  ◼   ◼  ¦cross  ¦    ◼    ¦ main 
¦         ¦  |    ¦    ◼    ¦  |
¦         ¦  |    ¦         ¦  |
+---------+  ↓    +---------+  ↓ 
  default        flex-direction: vertical
```
>Note: flex-direction: horizontal == default

## Properties

Some apply to containers and other to items.

### Main-axis alignments (horizontal by default)

The `justify-content` property apply to the `container`.
It defines the horizontal alignments of its items.

```markdown
+---------+   +---------+   +---------+
¦ ◼◼◼     ¦   ¦   ◼◼◼   ¦   ¦     ◼◼◼ ¦ 
+---------+   +---------+   +---------+ 
 Flex-start      center       flex-end

+---------+      +---------+
¦ ◼  ◼  ◼ ¦      ¦◼   ◼   ◼¦
+---------+      +---------+
space-around     space-between
```
### Cross-axis alignments (vertical by default)

The `align-items` property apply to the `container`.
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

> You can target a specific item with `align-self` property on the item.

### Wrapping items

Let the overflow item wrap and create a grid with the `flex-wrap` property.
It apply to the `container`.

```markdown
+---------+        +---------+
¦ ◼ ◼ ◼ ◼ ¦◼ ◼ ◼   ¦ ◼ ◼ ◼ ◼ ¦
¦         ¦        ¦  ◼ ◼ ◼  ¦
¦         ¦        ¦         ¦
¦         ¦        ¦         ¦
+---------+        +---------+
  nowrap               wrap 
```  
### Flex direction

The `flex-direction` property apply to the `container`.
It refers whether its items are render horizontally or vertically.

```markdown
+---------+   +---------+
¦         ¦   ¦    ◼    ¦
¦ ◼ ◼ ◼ ◼ ¦   ¦    ◼    ¦
¦         ¦   ¦    ◼    ¦
¦         ¦   ¦    ◼    ¦
+---------+   +---------+
    row          column
```

>Note: When rotating the direction of a container, the properties `justify-content` and `align-items`
> are inverted [More on this.](https://internetingishard.netlify.app/html-and-css/flexbox/index.html#alignment-considerations)

## Grouping flex items

Flex containers only know the position of elements one level below.
It means you can group flex items by wrapping them inside an extra div.

```markdown
A                B
+---------+      +---------+
¦◼   ◼   ◼¦      ¦◼     ◼ ◼¦
+---------+      +---------+
No grouping      Grouped items
```

In example B, the two items on the right are group in a common div.
The flex container treat this div as a single item and does not apply to the items inside.

## Placing flex item

`Flex item` can be placed more precisely inside their container with the `margin` property.

```markdown
A                B
+---------+      +---------+
¦◼◼◼      ¦      ¦◼      ◼◼¦
+---------+      +---------+
default place    margin-left: auto; on the middle item 
```

## Gap property

Applied on the `flex container`, set a gab between the items.

```css
.container {
  gap: 2px;
}
```


[flexbox cheatsheat](https://flexbox.malven.co/)

[source](https://internetingishard.netlify.app/html-and-css/flexbox/index.html)
[source2](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)
[source3](https://www.theodinproject.com/lessons/foundations-growing-and-shrinking)

