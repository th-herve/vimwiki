# === PowerShell Object and Array ===

Object have properties and methods

List the properties:

```powershell
"hello" | Get-Member - MemberType Property
```

Use the properties

```powershell
"hello".Length
    5
```



# String method

```powershell
$my_string = "hello, world"
$my_string.Contains("world")
    True


$my_string.Replace("world", "hi")
```



# Creating objects

```powershell
$dog = New-Object -TypeName PSCustomObject
```

### Adding propertties and methods

```powershell
// properties
$dog | Add-Member -MemberType NoteProperty -Name "Name" -Value "Medor"

// methods
$dog | Add-Member - MemberType ScriptMetthod -Name "Speak" -Value {Write-Host "Woof!"}
```

### creating object with hash table

```powershell
$dog = [PSCustomObject]@{
    Name = "Medor"
    Age = 10
}
```





# Array

Creating 

```powershell
$my_arr = 25, "test", $False
or
$my_arr = @(25, "test, (Get-Date).DateTime)
```

Accessing

```powershell
$my_arr[0] // one item

$my_arr[0,1] // each item


$my_arr[1..5] // from to


$my_arr[-1]
```

Iteration

```powershell
$my_arr.ForEach({ $PSItem.Length })
```



## Operator for arrays

```powershell
$arr_1 = 1, 2, 3
$arr_2 = 4, 5, 6
$arr_1 + $arr_2

$arr_1 * 2
```



Containment operators

* `-contains`: <array> -contains <item>
* `-notcontains`: <array> -notcontains <item>
* `-in`: <item> -in <array>
* `-notin`: <item> -notin <array>

-join

convert array into string join by a given string

```powershell
$my_arr = 1, 2, 3
$my_arr = $my_arr -join "->"
$my_arr
    1->2->3
```



Force a type

```powershell
[String[]]$fruits = "apple", "banana"
```



Array of objects

```powershell
$dog_arr = @(
    [PSCustomObject]@{Name = "Rufus"; Age = 10}
    [PSCustomObject]@{Name = "Medor"; Age = 6}
)
```
