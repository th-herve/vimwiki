# Regex

## Flag

Flag are modifier that change the output of a regex expression.  
Place the flag after the second `/`: /expression/flag

 
| flag | name             | action                    | input        |
|------|------------------|---------------------------|--------------|
| g    | global           | select in all             | /\W+\.com /g |
| m    | multiline        | select in all line        | /\W+\.com /g |
| i    | case-insensitive | select case insensitively | /\W+\.com /i |

## Basics expression

> string used in example: bar bor. boo bir 

- `[]` is a character class. It always match `one` character.

| key      | action                 | example    | output           | case sensitive |
|----------|------------------------|------------|------------------|----------------|
| .        | select all !char!      | /./g       | bar bor. boo bir |                |
| []       | alternative char       | /b[aoi]r/g | bar bor bir      |                |
| [^]      | exclude char           | /b[^o]r/g  | bar bir          |                |
| [a-z]    | letter range           | /b[i-z]    | bor bir          | yes            |
| [0-9]    | number range           |            |                  |                |
| [a-z0-9] | number or letter range |            |                  |                |
| \        | escape character       | / \./g     | .                |                |

> `Note`: to match `-` as a character instead the bracket, put it in first or last (the order does not matter): [-a-z] match - and a to z


| key | action                              | example    | output                                                       |
|-----|-------------------------------------|------------|--------------------------------------------------------------|
| ^   | select matching start of line       | /^[0-9]/g  | select all digit at the start of a line                      |
| $   | select matching end of line         | /html$/g   | select all html expr that are in the end of a line           |
| \w  | select letter,number and underscore | / \w /g    | a b 1 2 _ ...                                                |
| \W  | except letter,number and underscore | / \w /g    | . : ! ? ...  (space too)                                     |
| \d  | select only digit                   | / \d /g    | 1 2 ...                                                      |
| \D  | except digit                        | / \D /g    | a b ...                                                      |
| \s  | only space                          | / \s /g    | ' '                                                          |
| \S  | except space                        | / \S /g    | you get it                                                   |
| \b  | is boundary                         | / \bvim /g | select vim alone but not vim in neovim                       |
| \B  | is not boundary                     | / \Bvim /g | select vim in neovim but not just vim                        |


## Quantifiers


- `Asterisk *`: after a character, indicate that this character may either: not appear at all, or appear once or more side by side.
- `Plus +`: after a character, indicate that this character may appear either once or more side by side

| input       | regex   | output      |
|-------------|---------|-------------|
| br ber beer | /be*r/g | br ber beer |
| br ber beer | /be+r/g | ber beer    |

`*` and `+` are greedy quantifiers. To make them non greedy use a `?` after them : `.*?`

- `Question mark ?`: after a char, indicate that it is optional.

| input        | regex      | output       |
|--------------|------------|--------------|
| color colour | /colou?r/g | color colour |

- `Curly braces {}`: after a char, indicate the number of time it can appear.
        - {n}:  only n times
        - {n,}: minimum n times
        - {n,x}: between n and x times


| input                 | regex       | output            |
|-----------------------|-------------|-------------------|
| ber beer beeer beeeer | /be{2}r/g   | beer              |
| ber beer beeer beeeer | /be{2,}r/g  | beer beeer beeeer |
| ber beer beeer beeeer | /be{2,3}r/g | beer beeer        |

## Grouping

- Group expression with the `parentheses ()`

| input           | regex       | output                              |
|-----------------|-------------|-------------------------------------|
| ha haa haaa haa | /(haa)/g    | group the 2 occurence of haa        |
| ha haa haaa haa | /(haa)-\1/g | the group is given the reference \1 |

- (?:expression): denote a non-capturing group

> In nvim, group by escaping the parentheses `\(group\)`, use the group with `\1 \2 ...`
> Example: %/s/'\(a\)'/\1/g -> replace `'a'` with just `a`

## Alternation

- `Pip |`: specifies that an expression can be in different expression.

| input       | regex             | output      |
|-------------|-------------------|-------------|
| rat cat dog | /cat｜`dog/g      | cat dog     |
| rat cat dog | /(c｜r)at｜`dog/g | rat cat dog |

>Note: the `|` in the table is not a pipe, because it make the table bug


## Lookahead/lookbehind

Need to use the flag `-P` to use them

- Positive lookahead: expression1`(?=expression)`: select expression1 if followed by expression in lookahead
- Negative lookahead: expression1`(?!expression)`: select expression1 if `not` followed by expression in lookahead

- Positive lookbehind: `(?<=expression)`expression1: select expression1 if preceded with expression in lookbehind 
- Negative lookbehind: `(?<!expression)`expression1: select expression1 if `not` preceded with expression in lookbehind 
 

| name                | input               | regex          | output |
|---------------------|---------------------|----------------|--------|
| Positive lookahead  | Date: 4 aug 3PM     | / \d+(?=PM)/g  | 3      |
| Negative lookahead  | Date: 4 aug 3PM     | / \d+(?!PM)/g  | 4      |
| Positive lookbehind | Code: 109 price: $5 | / (?<=$)\d+/g  | 5      |
| Negative lookbehind | Code: 109 price: $5 | / (?<!\$)\d+/g | 109    |

In nvim, the syntax is different,
If we want to select text, depending on the 'look' word:

|          | Lookbehind       | lookahead       |
|----------|------------------|-----------------|
| positive | \(look\)\@<=text | \(look\)\@=text |
| negative | \(look\)\@<!text | \(look\)\@!text |

A simpler version in nvim is to use `\zs` for positive lookbehind and `\ze` for positive lookahead (there is no negative version).
T

|          | Lookbehind       | lookahead       |
|----------|------------------|-----------------|
| positive | look\zstext      | text\zelook     |

## Other

### Usage with grep

Use `-P` use perl regex style.

```bash
grep -P "regexhere \d+" file.txt
```

### Vim 

Use `\v` before the regex to use perl regex style.

```regex
/\v\d+
```

For `\b` word boundary use `<` and `>` :
```regex
/\v<vim>
```

The non greedy equivalent of `*` and `+` are : `{-}` and `{-1,}`
