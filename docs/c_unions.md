# C union

An unions allow one variable to hold data of different type and size.  
The variable will be big enough to hold the largest type.

The type retrieve must be the most recently stored.  
It's to the developer to keep track of the type.

```c
union u_tag {
  int   ival;
  float fval;
} u;
```
