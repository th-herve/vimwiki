# Sql query keywords

## WHERE

Filter query

```sql
SELECT * FROM student 
WHERE house = "Griffindor";
```

## LIKE

Used with % to search partial word

In the example, select student where name start with Pot...
```sql
SELECT * FROM student
WHERE name LIKE "Pot%":
```
% can be use after, before or both: Pot%, %tter, %tt%

## NOT

Invert a query result.

```sql
SELECT *
FROM students
WHERE house NOT IN ('Griffindor', 'Slitherin');

SELECT *
FROM students
WHERE NOT muggle; -- if muggle is a boolean
```

## ORDER BY

Order the selection.  
By default ascending, but canspecify descending with DESC

```sql
SELECT * FROM student
ORDER BY name DESC;
```

You can specify a secondary sort option:

```sql
SELECT * FROM student
ORDER BY name DESC, id ASC;
```

## LIMIT

Limit the number of result.  
Often use with ORDER BY to have the firsts or lasts items

example: select 10 best student by grade

```SQL
SELECT * FROM student
ORDER BY grade DESC
LIMIT 10;
```

## GROUP BY

Group the result by a column value.

example: count the number of student per house

```sql
SELECT COUNT(name) FROM student
GROUP BY house;
```

## IN

Check if a value is in a given list.  
can be use in subquery

```sql
SELECT name FROM student 
WHERE name IN (student1,student2...);
```
