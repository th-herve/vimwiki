# Css position property

The `position` property has 5 possible value:

- `static`: default position
- `relative`: position the element relative to `itself`
- `absolute`: absolute position in a given container
- `fixed`: relative to the `viewport`
- `sticky`: static, until you scroll past it, it become fixed.

## Static

Default for every element. The only case where you would use it, is to
override an inherited position (which is rare).

## Relative

It offset the element relative to its original position. By itself it does not
change the position. You modify it with the property `top`, `left`, `bottom`, `right`.

```css
/* push the element 10px down */
div {
  position: relative;
  top: 10px;
}
```

The moved elements will retain its original position in the flow of the 
document. Meaning if we push a relative element to the left, it will not 
push the other elements to the left.

It will however appear on top of an element if the new position overflow on 
this element. (It create a higher z-index value).

## Absolute

Place the element in an absolute position either in the whole document, or,
if present the first parent that has an `absolute` or `relative` position.

Adjust the position with the property `top`, `left`, `bottom`, `right`.

It remove the element from the `flow` of the document, and if overused can
reduce the flexibility of a site.

## Fixed

Position relative to the `viewport`. Meaning the position does not change if
the window is scrolled.

Most use to make navigation bar stay on top of the page.

 ```css
 header {
   position: fixed;
   top: 0;
   left: 0;
   with: 100%;
 }
 ```
 
 ## Sticky
 
 A sticky element is static, but as you scroll past it, if it's parent element
 has room, it become fixed. Until the parent is out of room.
