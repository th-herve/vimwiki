# Html form validation

Client-side validation of a form can be implemented in html.

`!!` Server-side validation is still necessary.

## Required validation

Specify required fields with the `required` attribute.

```html
<input id="user_email" type="email" name="user_email" required>
```

## Text length validations

- `minlength`: specify the minimum amount of characters.
- `maxlength`: specify the maximum amount of characters.

```html
<textarea minlength="5" maxlength="20"></textarea>
```

## Number range validations

- `min`: minimum value.
- `max`: maximum value.

```html
<input type="number" min="1" max="5">
```

## Pattern validation

A [regular expression](regex.md) can be used to validate fields.
Define it the `pattern` attribute.

[list of common pattern](https://www.html5pattern.com/)

To add a error message that inform the pattern to match to the user,
use the `title` attribute.

```html
<input type="text" name="zip_code" pattern="(\d{5}([\-]\d{4})?)" title="Please enter a valid zip code, example: 53290">
```

## Styling validation

In css, use the pseudo-class `:valid` and `:invalid` to style the element
based on its validation statue.
