# Css form

A form is wrap in a `form` element. Which take two essential attributes:

- `action`: the url to send the data to
- `method`: POST or GET


```html
<form action="example.com/path" method="post">
  <label for="first_name">First Name:</label>
  <input type="text" id="first_name">
</form>
```

## input element

Most versatile element, accepts a `type` attribute that determine the type of
information collected. 

To add a text above it, add a `label` element with a `for` attribute value
that match the `id` of the input.

```html
  <input type="text" id="first_name" placeholder="your name" name="first_name">
  <label for="first_name">First Name:</label>
```
#### Attributes:

- `type`: type of information collected
- `id`: must match the `for` attribute in the label
- `placeholder`: text display by default
- `name`: name used when send to the backend
- `value`: value send to the backen (for checkbox, radio...)

#### Type attributes:

- `text`
- `email`
- `password`
- `number`
- `date`
- `checkbox`
- `radio`

## text area element

Let the user enter a longer text, like a comment.

```html
<textarea id="" name="" cols="30" rows="10">Placeholder text</textarea>
```

## Select dropdown

Wrap it in a `<select>` with each option in its own `<option>`
You can group the option inside a `<optgroup>`

Add the attribute `selected` to an option to have it as default.

```html
<select name="Car">
  <optgroup label="big">
      <option value="mercedes" selected>Mercedes</option>
      <option value="tesla">Tesla</option>
      <option value="volvo">Volvo</option>
  </optgroup>
  <optgroup label="small">
      <option value="bmw">BMW</option>
      <option value="mini">Mini</option>
      <option value="ford">Ford</option>
  </optgroup>
</select>
```

## Checkboxes

Box where several option can be checked. Can also have only 
one option to have a toggle.

It is an `<input>` with the `type` set as `checkbox`.

All the option must have the same `name` attibute.

```html
<h1>Pizza Toppings</h1>

<div>
  <input type="checkbox" id="sausage" name="topping" value="sausage" checked>
  <label for="sausage">Sausage</label>
</div>

<div>
  <input type="checkbox" id="onions" name="topping" value="onions">
  <label for="onions">Onions</label>
</div>
```

## Radio buttons

Checkbox where only one option can be checked.
It is an `<input>` with the `type` set as `radio`.

All the option must have the same `name` attibute.

```html
  <ul>
    <li>
      <label for="soup">Soup</label>
      <input type="radio" id="soup" name="meal" value="soup" checked />
    </li>
    <li>
      <label for="pizza">Pizza</label>
      <input type="radio" id="pizza" name="meal" value="pizza" />
    </li>
  </ul>
```

## Buttons

Three type:

- `submit`: send the form
- `reset`: clear the value entered in the form
- `button`: generic button that can be whatever you want (set with js)

```html
<button type="submit">Submit</button>
<button type="reset">Submit</button>
<button type="button">Submit</button>
```

## Organizing form elements

### Fieldset

A `<fieldset>` is a container that group related form input into
a ligical unit.

```html
<fieldset>
    <label for="first_name">First name</label>
    <input type="text" id="first_name" name="first_name">
    
    <label for="last_name">Last name</label>
    <input type="text" id="last_name" name="last_name">
</fieldset>
```

### Legend

It is the title of a `fieldset`, it should come right after this one.

```html
<fieldset>
    <legend>Contact detail</legend>
    <label for="first_name">First name</label>
    <input type="text" id="first_name" name="first_name">
    
    <label for="last_name">Last name</label>
    <input type="text" id="last_name" name="last_name">
</fieldset>
```
