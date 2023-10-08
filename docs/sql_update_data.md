# Sql update data

To update data in a table, use the following syntax:

```sql
UPDATE <table name> 
SET <column name> = <value> 
WHERE <condition>;
```
For example, to update the "age" of a student named "Alice":
```sql
UPDATE students 
SET age = 21 
WHERE name = 'Alice';
```
