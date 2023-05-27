# === PowerShell Environment Variables ===

In PowerShell, environment variables are stored as string

List them:

```powershell
Get-Children Env:
(Get-Children Env:USERNAME).Value
```

Create one:

```powershell
$Env:EXEMPLE_ENV_VAR = "custom value"
```

> Note: environment variable name are in upper case
