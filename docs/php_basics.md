# Php basics

You can write html directly in a .php file. 
To enter php mode, write code inside a self closing `<?php code here ?>` tag.

In a .php file:
```php
<p>This code will be delivered as it is</p>
<?php 
echo "<p>This code is interpreted by php and turned into HTML</p>;"
?>
```

If used in the cli, it's common practice to not close the <?php tag

```php
<?php
// code here with no closing tag
```

## Comment

Use `//` or `/* text */`

```php
// Comment

/*  multi line
    comment */
```

## String concatenation

```php
<?php
echo "one " . "two";
```

## Variable

```php
<?php
$my_variable = "hello";
echo $ my_variable;
```
