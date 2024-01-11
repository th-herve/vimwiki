# Sql join

Allow to select and organise data from different table by joining them.  

## Syntax

```sql
SELECT * 
FROM assignments JOIN houses ON houses.id = assignments.house_id
WHERE houses.house = "Gryffindor";
```

```sql
SELECT a.*, h.name
FROM assignments a JOIN houses h ON h.id = a.house_id
WHERE houses.house = "Gryffindor";
```
## Syntax with sub-query

Can be useful to remove duplicate.

```sql
SELECT *
FROM houses
WHERE id IN (SELECT house_id     -- the sub-query must return the same type as the one in the where statement
            FROM assignments
            WHERE 'class' = 'charms')
```
> Can be sometime optimised by using `NOT IN` instead. Choose the one that will result with the smallest sub-query.

## Old syntax

Before sql2, the join keyword did not exist.

```sql
SELECT *
FROM houses, assignments
WHERE houses.id = assignments.house_id
```
> Very ineffective method, do not use.
