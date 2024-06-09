# Git config

Global config and local config.

- a key = <section>.<key>

Add a key  value :
```bash
git config --add --global <section>.<key> "<value>"
```

View key value :
```bash
git config --get <section>.<key>
```

>Note: you can add the same <section>.<key> several time with different value.

## List config keys

```bash
git config --list
# or
git config --get-regexp <regex>
```

## Remove config key

```bash
git config -unset <section>.<key>
git config -unset-all <section>.<key> # if the key has several entry

git config -remove <section> # remove all sections
```

## Config files

The final config is the result of the merge of several files.
They are `--system`, `--global`, `--local`, `--worktree`

Without specifying it is `--local`.
