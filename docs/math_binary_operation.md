# Binary operation

## Addition

```latex
                      ₁       ₁
  0      1      0      1      1 
 +0     +0     +1     +1     +1
----   ----   ----   ----   ----
  0      1      1     10     11
```

## Subtraction

```latex
                       
  0      1      1 
 -0     -0     -1 
----   ----   ----
  0      1      0 
```

Case when in one column there is the operation 0₂ - 1₂:
1. We can't do 0₂ - 1₂. So we have to borrow a 1 from the next column.
2. We note 1 next to the top 0:
    The top part become 10₂ (or 2₁₀)
    So we have 10₂ - 1₂ (or 2₁₀ - 1₁₀) which gives 1₂
3. Since we took 1 from the next column, we remove it from it by noting a little 1₂ at the bottom part

`!!` Note that when at the top or bottom the little 1₂ do not have the same weight. In the top it is really 10₂ and at the bottom 1₂
So if there is a big one with it, at the top it is 10₂ + 1₂ = 11₂ and at the bottom 1₂ + 1₂ = 10₂

```latex
    ₁
   10 
 - ₁1 
------
   01
```     



₁₀
₁₆
₂
