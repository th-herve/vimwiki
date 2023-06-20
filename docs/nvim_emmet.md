# Nvim emmet

Abbrevation engine for expanding html code.

## Basic use

Type the expression to expand and type `<C-y>,` by default.
Or set it to double coma `,-,`.

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
div#page>div.logo+ul#navigation>li*5>a

<!-- result -->
   <div id="page">
        <div class="logo"></div>
        <ul id="navigation">
            <li><a href=""></a></li>
            <li><a href=""></a></li>
            <li><a href=""></a></li>
            <li><a href=""></a></li>
            <li><a href=""></a></li>
        </ul>
    </div>
```
