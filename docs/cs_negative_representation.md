# Cs negative representation

In two's complement, the left most bit represent the sign. 
0 for positive numbers and 1 for negative.

```c
0b0000 0001 // is positive
0b1000 0001 // is negative !!it's not -1
```
The most significant bit is represented by `minus` 2 to the power its position:

| 0    | 0   | 0   | 0   | 0   |
|------|-----|-----|-----|-----|
| -2^4 | 2^3 | 2^2 | 2^1 | 2^0 |

To get the negative number, add each bits together, with the most significant bit being negative.

### Example for 1000 0001

1000 000`1` = +1
`1`000 0001 = -128

So 1000 0001 = 1-128 = `-127`

### Example for 1111 1111

1`111 1111` = 1+2+4+8+16+32+64 = 127
`1`111 1111 = -128

So 1111 1111 = 127-128 = `-1`

### Example for 1000 0000

`1`000 0000 == -`128`


## Calculation

To calculate the value of a negative number, flip all the bits and add one: `-x = ~x + 1`

101 100
010 011 (flip the bits)
010 100 (add 1)
010 100 = 16+4 = 20
So it's -20

>Note: work the other way around, flip and add 1 to a positive number gives its negative representation.

## Converting a number to a larger space

To increase the memory size of a number, while keeping its value, in two's complement, for a positive number, simply add leading `0`:

`0101 == 0000 0101`

For a negative number, add leading `1`:

1101 == 1111 1101
