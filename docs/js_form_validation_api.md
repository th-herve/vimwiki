# Javascript form validation API

The `constraint validation API` is a set of methods and properties
available on the following form elements:

- <button>
- <fieldset>
- <input>
- <output>
- <select>
- <textarea>

Some also work on the <form> element.

## Methods

### Validity

example:

```javascript
// return true element too long
button.validity.tooLong
```
Can be used with:

- patternMismatch
- tooLong/tooShort
- rangeOverflow/rangeUnderflow
- typeMismatch (with type=url or email)
- valid: return true the element meets all validation constraint
- valueMissing

[full list](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState)

## setCustomValidity

Set a custom error message

```javascript
const email = document.getElementById("mail");
 
email.addEventListener("input", (event) => {
  if (email.validity.typeMismatch) {
    email.setCustomValidity("I am expecting an email address!");
  } else {
    email.setCustomValidity("");
  }
});
```
