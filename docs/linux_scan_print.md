# Linux scan print

## Scan

```bash
scanimage --output-file filename.pdf

# with a given device (might solve some problems)
scanimage --device "airscan:ei:HP..." --output-file filename.pdf

```
The defaut scaner can be set by exporting the variable `SANE_DEFAULT_DEVICE`

## Print

```bash
lp filename.pdf
```

