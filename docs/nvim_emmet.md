# Nvim emmet

Abbrevation engine for expanding html/css code.

[Doc](https://github.com/mattn/emmet-vim/blob/master/doc/emmet.txt)

## Basic use

Type the expression to expand and type `<C-y>,` by default.
Or set with custom key `<M-,>,`

```html
<!-- expression -->
!

<!-- result -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title></title>
</head>
<body>

</body>
</html>
```
## example of expression

```html
div#page>div.logo+ul#navigation>li#foo$*5>a

<!-- result -->
<div id="page">
  <div class="logo"></div>
  <ul id="navigation">
    <li id="foo1"><a href=""></a></li>
    <li id="foo2"><a href=""></a></li>
    <li id="foo3"><a href=""></a></li>
    <li id="foo4"><a href=""></a></li>
    <li id="foo5"><a href=""></a></li>
  </ul>
</div>
```
## Update tag

Add a class or id to a tag

1. Cursor on opening tag
2. Press `,-u`
3. enter the class/id: `.my-class` `#my-id`

## Add tag

1. Select the text you  want in one or several tag.
    ```html
    test1
    test2
    test3
    ```
2. Press `,-,` and enter the tag(s)
3. For example `div>a*` result:
    ```html
    <div>
      <a href="">test1</a>
      <a href="">test2</a>
      <a href="">test3</a>
    </div>
    ```
    
## Other
    
key to press before leader key.

| key             | result                        |
|-----------------|-------------------------------|
| p,div,link,a... | <p></p>...                    |
| .className      | <div class="className"></div> |

Expression operators

| operator | description    | example                       |
|----------|----------------|-------------------------------|
| >        | child          | div>p                         |
| +        | sibling        | div>p+a                       |
| ^        | climb-up       | div>p^div                     |
| *        | multiplication | div*2>p*3                     |
| ()       | grouping       | div>(header>ul>li*2)+footer>p |

This work to create 3 pair of <p> and <a> in the second div:
> (div>div>(p+a)*3)+footer>p

Attribute operators

| operator | description                     | example            |
|----------|---------------------------------|--------------------|
| .        | class                           | div.class1.class2  |
| #        | id                              | span#id1           |
| []       | custom attribute                | a[href="link"]     |
| $        | number (with the * op)          | ul>li.item$*4      |
| @        | use with $, change the ordering | ul>li.item$@*4     |
| {}       | add text inside tag             | button{click me}   |

>Note: the "*" in the table are not visible in vimwiki 
