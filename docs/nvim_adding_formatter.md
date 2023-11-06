# Nvim adding formatter

1. Run `:mason`
2. Press `5` to have the formatter list
3. Press `i` to install a formatter
4. Open the lsp config file
5. Find `null_ls.setup({ ... })`
6. Add in the `sources` list: `formatting.name,`
7. Should work!
