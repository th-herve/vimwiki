# Java tips

## Increment value in map

Increase map value for a given key by 1, or set it to one if key does not exist yet.
```java
map.merge(key, 1, Integer::sum);
```
