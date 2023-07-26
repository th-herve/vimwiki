# Awk

Text processing tool. Manipulate and analyse text 
files in a line by line manner. 
Useful for extracting fields, filtering data, performing calculations.

## Basics

```bash 
awk 'pattern { action }' input_file
```
- Pattern: optional condition, if met, trigger the action.
- Action: action(s) performed on each lines that match the pattern.
- Input file: if omitted it takes the standard input.

## Print command

Print for each lines the given field. By default, fields are separated
by spaces. The field to print is specified with `$n`.

```bash
awk '{ print $2, $3 }' input_file
```
The field separator can be specified with the `-F` flag.

```bash
awk -F ',' '{ print $5 }' input_file
```

## Built in variable

- `NR` current line number
- `NF` number of fileds in current line
- `$0` entire current line
- `$1`, `$2`...individual fields of current line

## Condition

```bash
awk '{ if ($1 > 10) print $0 }' input_file
```
