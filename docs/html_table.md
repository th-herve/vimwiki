# html table

## Create a table

1. A table is enclosed in a `<table>` tag
2. Each cell is in a `<td>` (table data)
3. Create row with `<tr>`  (table row)
4. Add header with `<th>` (table header)

```html
 <table>
  <tr>
    <th>header 1<th/>
    <th>header 2<th/>
  <tr/>
  <tr>
    <td>1st row first cell<td/>
    <td>1st row second cell<td/>
  <tr/>
  <tr>
    <td>2nd row first cell<td/>
    <td>2nd row second cell<td/>
  <tr/>
<table/>
```
Result:

| HEADER 1           | HEADER 2            |
|--------------------|---------------------|
| 1st row first cell | 1st row second cell |
| 2nd row first cell | 2nd row second cell |

## Let cells take multiple row or columns

Use the `colspan` and `rowspan` attributes on the `td` tag.

```html
<table>
  <tr>
    <td>1st row first cell<td/>
    <td>1st row second cell<td/>
  <tr/>
  <tr>
    <td colspan="2">2nd row big cell<td/>
  <tr/>
<table/>
```

## Styling

You can I add css style to each <td> separately, or you can use
the `<colgroup>` tag with the `<col>` tag to define, in `html` the
style of each columns.

```html
<table>
  <colgroup>
    <col />
    <col style="background-color: red; width: 42px" span="2" />
  <colgroup/>
  
  <tr>
    <td>1st row first cell<td/>
    <td>1st row second cell<td/>
    <td>1st row third cell<td/>
  <tr/>
  <tr>
    <td>2nd row first cell<td/>
    <td>2nd row second cell<td/>
    <td>2nd row third cell<td/>
  <tr/>
<table/>
```
In the example, the first row has no style applied but is still specify with `<col />` and
the second and third row have red background and 42px width apply. It apply on the two columns
with the `span` attribute.

## Advanced

### Adding caption

Add a text above the table with the `<caption>` tag.

```html
<table>
  <caption>
    Title of the table.
  <caption/>
  
  <tr>
    <td>1st row first cell<td/>
    <td>1st row second cell<td/>
  <tr/>
<table/>
```

### Adding structure

In more complex table, define the structure with `<thead>`, `<tfoot>` and `<tbody>`.

It is useful for styling with css.

```html
<table>
  <thead>
    <tr>
      <th>Header 1<th/>
      <th>Header 2<th/>
    <tr/>
  <thead/>
  <tfoot>
    <tr>
      <td colspan="2">footer text<td/>
    <tr/>
  <tfoot/>
  <tbody>
    <tr>
      <td>1st row first cell<td/>
      <td>1st row second cell<td/>
    <tr/>
  <tbody/>
<table/>
```

## Scope

To make the table easier to read for screen reader, use the `scope` attribute on the header.
Either for column or row.

The value possible are: `row`, `col`, `colgroup` and `rowgroup`.

```html
<table>
  <tr>
    <th scope="col">Header 1<th/>
    <th scope="col">Header 2<th/>
  <tr/>
  <tr>
    <td>1st row first cell<td/>
    <td>1st row second cell<td/>
  <tr/>
<table/>
```
