# Sql jointures

Allow to select and organise data from different table by joining them.  

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
