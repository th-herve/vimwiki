# === PowerShell command ===

## file related command

### Open file

```PowerShell
$file = Get-Comtent -Path "C:\Path\to\file.json" -Raw
```
>note: the -raw make it return the entire file as a string instead of an array of strings

### Convert file to PowerShell object

The file must be converted to an PowerShell object before being manipulated

```PowerShell
$obj = $file | Convert-From-Json
```
