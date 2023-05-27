
# === PowerShell control flow ===

## if 

```PowerShell

$my_var = 2
if ($my_var -eq 2){
    Write-Host "it is true"
} elseif($my_var -gt 2) {
    Write-Host "whatever"
} else {
    Write-Host 'idk'
}
```
## switch


```PowerShell
$var = 5
switch ($var) {
    10 {Write-Host "it is 10"}
    5  {Write-Host "it is 5"}
    default {Write-Host "other"}
}
```

Can be used with conditional expressions, us $_ to refer to the variable


```PowerShell
$myVar = 10
switch ($myVar) {
  {$_ -gt 5} {Write-Host "Greater than 5"}
  {$_ -gt 0} {Write-Host "Greater than 0"}
}
```
>note: every condition are check and if true executed
