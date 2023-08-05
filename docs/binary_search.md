# Binary search

Work on a `sorted array`, to find a given item.

## Implementation

1. Calculate middle point of the current (sub)array
2. It the target is in the middle `stop`
3. Otherwise:
  1. if target < middle -> repeat changing the end point to the left of the middle
  2. if target > middle -> repeat changing the start point to the right of the middle
