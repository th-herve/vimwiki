# C enumeration

In c, an enumeration is a list of `constant` integer values.

The values start at 0, but can be explicitly specified.  
If not all values are specified, the progression continues from the last specified value.

```c
// first one is set to one instead of 0, the rest follow automatically
enum month {JAN = 1, FEB, MAR, APR, MAY, JUN, JUL, AGU, SEP, OCT, NOV, DEC}
```

Variable can be created from an enum:

```c
enum month this_month = FEB;
```
