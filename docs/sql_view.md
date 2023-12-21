# Sql view

Create a fictive table that can then be referenced in a query.

## Basic syntax

```sql
CREATE VIEW Griffindow_student AS
SELECT student_name, student_grade
FROM student
WHERE house = 'Griffindor'; 

-- can be use in queries
SELECT * FROM Griffindow_student;
```
## Advanced example

`!!` to join two table, don't use JOIN, select the tables and add a WHERE statement

```sql
CREATE VIEW Griffindow_student AS
SELECT s.student_name, AVG(g.grade) AS average_grade   -- don't forget the AS if using a function
FROM student s
JOIN grade g ON s.student_id = g.student_id
WHERE s.house = 'Griffindor'
GROUP BY s.student_name; -- don't forget to group if using an aggregate function
```
