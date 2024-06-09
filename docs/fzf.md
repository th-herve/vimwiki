# Fzf

## set up

To get the keybinds and other utilities, add this in `.zshrc` :

```bash
eval "$(fzf --zsh)"
```

## Autocomplete

Use `C-t` to list all files and directories.
Use `M-c` to list directories.
Use `C-r` to open the command history in fzf.

Autocomplete command by typing it followed by `**` and `Tab`:

```bash
nvim **<Tab>

cd **<Tab>

kill -9 **<Tab> # complete with running process

ssh **<Tab> # complete the ip used
```
The search can be more specific :

```bash
nvim .py**<Tab> # search all .py file
nvim ~/Downloads/**<Tab> # search in the Downloads directory
```

## Search token

| Token     | Match type                 | Description                          |
| --------- | -------------------------- | ------------------------------------ |
| `sbtrkt`  | fuzzy-match                | Items that match `sbtrkt`            |
| `'wild`   | exact-match (quoted)       | Items that include `wild`            |
| `^music`  | prefix-exact-match         | Items that start with `music`        |
| `.mp3$`   | suffix-exact-match         | Items that end with `.mp3`           |
| `!fire`   | inverse-exact-match        | Items that do not include `fire`     |
| `!^music` | inverse-prefix-exact-match | Items that do not start with `music` |
| `!.mp3$`  | inverse-suffix-exact-match | Items that do not end with `.mp3`    |
