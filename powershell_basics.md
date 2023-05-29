
# === PowerShell Basics ===

# Basic CmdLets

Verb-Noun

Exemple:

- Get-Date

- Write-Host

- Get-Command

- Clear-host
  
  

## Flags

| Flag   | Do |
|--------|----|
| -Verb  |    |
| -Nouns |    |

# variable

create:

```powershell
$my_variable = "hello"
```

Use:

```powershell
$my_variable
hello
```

user imput:

```powershell
$my_input = Read-Host -Prompt "enter a number"
```

Enforce type:

```powershell
[Int]$age = 25
```

Create multiple variables:

```powershell
$i = $j = $k = 0
$number, $color = 25, "red"
```

## Method

```powershell
$variable.GetType().Name
```



## Arithmetic operators

- +

- -

- *

- /

- %

## Comparison operators

| operator | meaning          |
|----------|------------------|
| `-eq`    | equal            |
| `-ne`    | not equal        |
| `-gt`    | greater than     |
| `-lt`    | lower than       |
| `-ge`    | greater or equal |
| `-le`    | lower or equal   |

```powershell
$my_num = 5
$my_num -ne 5
    False
7 -gt 2
    True
```



## Logical operator

- `-and`

- `-or`

- `-xor`

- `-not` or `!`
