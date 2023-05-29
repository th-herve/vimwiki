# === PowerShell manipulate json file ===

To manipulate JSON files with PowerShell, you can use the ConvertFrom-JSON cmdlet to parse JSON data into PowerShell variables, and the ConvertTo-Json cmdlet to convert PowerShell objects to JSON [Source 4]. Here are the steps to retrieve, modify and save a JSON file:

## Retrieve JSON file

1. Open PowerShell.

2. Use the Get-Content cmdlet to retrieve the content of the JSON file and store it in a variable.

```PowerShell
$jsonString = Get-Content -Path "path/to/file.json"
```
>Note: -Raw can be added at the end to have it as a single string instead of array of strings

3. Use the ConvertFrom-JSON cmdlet to convert the JSON string to a PowerShell object.

```PowerShell   
$jsonObject = ConvertFrom-JSON $jsonString
or
$jsonObject = $jsonString | ConvertFrom-Json
```

4. Now you can access the object properties to retrieve or modify the values.


## Modify JSON file

1. Use the dot notation to access the object properties and modify their values.

```PowerShell
$jsonObject.SystemName = "NewSystemName"
```
2. Use the Add-Member cmdlet to add a new property to the object.

```PowerShell
$jsonObject | Add-Member -Name "PSVersion" -MemberType NoteProperty -Value "7.0"
```
3. Use the ConvertTo-JSON cmdlet to convert the PowerShell object back to a JSON string.

```PowerShell
$newJson = $jsonObject | ConvertTo-JSON
```
>Note: -Depth x, where x is a int, can be added at the end to specify how many levels deep the conversion should go.   
Can be useful for complex object with nested property

## Save JSON file

1. Use the Set-Content cmdlet to save the JSON string to a file.
```
Set-Content -Path "path/to/file.json" -Value $newJson
```
