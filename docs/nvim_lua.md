# Nvim lua


## unload a module

```lua
package.loaded["pluginName.utils"] = nil
```

## Print table

```lua
vim.print(table)

--or 

print(vim.inpect(table))
```

## Run current module

```lua
source %
```
