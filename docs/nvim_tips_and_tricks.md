
# Nvim tips and trick

## auto increment list

transform:

```bash
1. 
1. 
1. 
```
into:

```bash
1.
2.
3.
```
- enter visual mode 
- select the number 1, except the first
- press g then C-a

## recording

You can record action and play them again

1. Start recording: press `q` followed by a register letter, for exemple `a`
2. Record your action (take into consideration the movement)
3. Stop recording: press `q`
4. Replay: press `@` followed by the register letter `@a`
5. To replay several time: `4@a`

## open file at a given line

```bash
nvim file.c + 46
```
