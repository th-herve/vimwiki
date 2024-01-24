# Numeral system
₁₀
₁₆
₂

## Conversion using the casio graph 35+

1. menu ->     run-mat
2. shift+menu (set up)
3. Mode -> select the system you want the result in
4. Select a numeral system you want to convert from with `F1` and then d for decimal, h for hexa, b for binary
5. type the number and presss exe

Note: when typing hexa number, do not use alpha.

## Binary

### Base 2 to 10

1. Decompose the base 2 number
2. Calculate the decomposition

Example: 1110.1₂
```latex
1*2^3 + 1*2^2 + 1*2^1 + 1*2^-1= 14.5₁₀
```

### Base 10 to 2

The integer and fractional part have to be converted separately.

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

#### Fractional part

1. Take the fractional part of the number
2. In a table, multiply it by 2
3. If result > 1 write 1 in binary else 0
4. Take the fractional part of the result and repeat until the desired number of floating point values is reached

Example: to convert the fractional part of 2.65₁₀

| Calculation     | Binary | rest |
|-----------------|--------|------|
| 0.65 * 2 = 1.30 | 1      | 0.3  |
| 0.3 * 2 = 0.60  | 0      | 0.6  |
| 0.6 * 2 = 1.20  | 1      | 0.2  |
| 0.2 * 2 = 0.40  | 0      | 0.4  |

The fractional part is .1010₂ with 4 number after the point


## Base 16 or hexadecimal
  
| Decimal     | 0    | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | 10   | 11   | 12   | 13   | 14   | 15   |
| hexadecimal | 0    | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | A    | B    | C    | D    | E    | F    |
| Binary      | 0000 | 0001 | 0010 | 0011 | 0100 | 0101 | 0110 | 0111 | 1000 | 1001 | 1010 | 1011 | 1100 | 1101 | 1110 | 1111 |

To get the corresponding letter for number above 9, add their digits together, and get the corresponding letter.
Ex for 12: 1+2=3, the 3rd letter of the alphabet is C.

### Base 2 to 16

Make group of 4 bits and convert them, starting from the right for decimal part and the left for fractional part, add 0 if necessary.   
101111,101011₂ = `00`10 1111,1010 11`00`₂ = 2F,AC₁₆

### Base 16 to 2

Convert each hexa number to it's corresponding byte.

### Base 10 to 16

1. Divide the number by 16
2. Note the remainder
3. Take the quotient and repeat step 1-3 the process until the quotient is 0
4. Then take the remainders from newest to oldest

### Base 16 to 10

```latex
A8B = 10 * 16^2 + 8 * 16^1 + 11 * 16^0 = 2 699
```
