# Cs bitwise operation

| x | y || & | I | ^ |
|---|---||---|---|---|
| 0 | 0 || 0 | 0 | 0 |
| 0 | 1 || 0 | 1 | 1 |
| 1 | 0 || 0 | 1 | 1 |
| 1 | 1 || 1 | 1 | 0 |

## & (and)

Take two numbers and perform a `and` on each bits, resulting in 1 if both are 1.

```c
int x = 0b001 & 0b011 // x = 0b001
```

## | (or)

Take two numbers and perform a `or` on each bits, resulting in 1 if either is 1.

```c
int x = 0b001 | 0b011 // x = 0b011
```

## ^ (xor)

Take two numbers and perform a `xor` on each bits, resulting in 1 if the two bits are differents.

```c
int x = 0b001 | 0b010 // x = 0b011
```

## ~ (complement)

Unary operator that change 1 to 0 and 0 to 1.

```c
int x = ~0b001 // x = 0b110
```

## >> (right shift)

Shift all bits to the right by a certain amount. Bits shifted off the end are lost.

```c
int x = 0b100 >> 2 //x = 0b001
int x = 0b100 >> 3 //x = 0b000
```
## << (left shift)

Shift all bits to the left by a certain amount, adding 0 to vacated position. Bits shifted off the end are lost.

```c
int x = 0b001 << 2 //x = 0b100
int x = 0b100 << 4 //x = 0b000 // the 1 is lost
```

## Tricks

- `|` with `1` turn a bit `on`
- `&` with `0` turn a bit `off`
- `|` can be use to find the `union` of bits
- `&` can be use to find the `intersection` of bits
- `^` can be use flip select bits
- `~` can be use flip all bits
 
