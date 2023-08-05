# Big O

[cheat sheet](https://www.bigocheatsheet.com/)

From fastest to slowest:
- O(1) - Constant complexity
- O(log N) - Logarithmic complexity
- O(N) - Linear complexity
- O(N log N) - N * log N complexity
- O(n²) - Quadratic complexity
- O(n³) - Cubic complexity
- O(2ⁿ) - Exponential complexity
- O(N!) - Factorial complexity

## O(1)

Always take one step (or a little bit more).

## O(log N)

Number of steps increase by 1 when data doubles.

Example: binary search

## O(N)

The number of step grows at the same rates as
the number of items.

## O(N log N)

When we loop over a collection, and for each items,
loops over another collection while reducing the data set.

Example: merge sort.

## O(n²)

When you loop over a data set and within each
loop, loop over it again.

## O(n³)

Triple nested loops.

## O(2ⁿ)

Each new item double the number of steps.

### O(N!)

Usually when calculating permutations.


