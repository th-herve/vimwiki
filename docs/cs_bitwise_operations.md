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
