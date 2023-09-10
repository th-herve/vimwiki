# Numeral system
₁₀
₁₆
₂

## Base 10 / Base 2

### Base 2 to Base 10

1. Decompose the base 2 number
2. Calculate the decomposition

Example: 1110.1₂
```latex
1*2^3 + 1*2^2 + 1*2^1 + 1*2^-1= 14.5₁₀
```

### Base 10 to Base 2

#### Integer part

1. Write in a table the power of 2 until it's greater than the number to convert
2. In the second line of the table, 
   If the power of two is greater than the number write 0,
   else write 1 and subtract, to the number, the corresponding power of two
3. Repeat step two until the number is 0

Example: 57₁₀

1. Write the power of two until 64 (first greater than 57)

| 2^n    | 64         | 32         | 16       | 8     | 4   | 2   | 1    |
| Binary | 0          | 1          | 1        | 1     | 0   | 0   | 1    |
|--------|------------|------------|----------|-------|-----|-----|------|
|        | 64>57 so 0 | 32<57 so 1 | 16<25: 1 | 8<9   | 4>1 | 2>1 | 1==1 |
|        |            | 57-32=25   | 25-16=9  | 9-8=1 |     |     | so 1 |

