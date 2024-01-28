# Bit hacks

## Set a given bit to 1

```c
// Set the nth bit to 1
x = (1 << n) | x
```

## Clear a given bit (set it to 0)

```c
// Set the nth bit to 0
x = ~(1 << n) & x
```

## Toggle a bit

```c
// toggle the nth bit
x = (1 << n) ^ x
```

## Replace trailing 0 by 1

```c
x = (x-1) | x
```

## Convert positive to negative representation

```c
x = (~x) + 1
// ex : 0010 -> 1110 = 2 -> -2
```

## Extract least significant 1 bit

Take advantage of the property that the negative and positive representation of a number in bits only share the least significant 1 bit.
For example 2 and -2, 00`1`0 and 11`1`0 share only the right most 1 is shared.

```c
x = x & -x
```
