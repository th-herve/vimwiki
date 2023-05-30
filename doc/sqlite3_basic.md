# SQLite3 Guide

To start using SQLite3 in a terminal, run the command:

```sql
sqlite3 <database name>.db
```
This will create a new database if the specified name does not already exist.
<br><br>
## Creating a Table

To create a new table, use the following syntax:
```sql
CREATE TABLE <table name> (
  id INTEGER,
  <column name> <data type>,
  PRIMARY KEY (id)
  ...
);
```
Typing primary key (id), allow to create and increment automatically the id each new entry

For example, to create a table called "students" with two columns "name" and "age":
```sql
CREATE TABLE students (
  id INTEGER,
  name TEXT,
  age INTEGER,
  PRIMARY KEY (id)
);

```


<br><br>

# Inserting Data

To insert data into a table, use the following syntax:
```sql
INSERT INTO <table name> (<column name>, ...) 
VALUES (<value>, ...
);
```
For example, to insert a new row into the "students" table:
```sql
INSERT INTO students (name, age)
 VALUES ('Alice', 20
 );
```

## Importing data from a csv file

Enter csv mode to specify that a csv file will be imported, then import it

```sql
.mode csv

.import <csv name>.csv <table name>
```

<br><br>

# Selecting Data

To retrieve data from a table, use the following syntax:
```sql
SELECT <column name>, ... 
FROM <table name>;
```
For example, to select the "name" column from the "students" table:
```sql
SELECT name 
FROM students;
```

### JOIN table
Allow to select and organise data from different table by joining them.  

```sql
SELECT * FROM assignments
JOIN houses ON houses.id = assignments.house_id
WHERE houses.house = "Gryffindor";
```
<br><br>

# Updating Data

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

<br><br>

# Deleting Data

To delete data from a table, use the following syntax:
```sql
DELETE FROM <table name> 
WHERE <condition>;
```

For example, to delete all students with an age less than 18:
```sql
DELETE FROM students
WHERE age < 18;
```

<br><br>

# Dropping a Table

To delete an entire table, use the following syntax:

```sql
DROP TABLE <table name>;
```
For example, to delete the "students" table:

```sql
DROP TABLE students;
```

<br><br>

# Query keywords

### WHERE

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

## ORDER BY

Order the selection.  
By default ascending, but canspecify descending with DESC

```sql
SELECT * FROM student
ORDER BY name DESC;
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

# Query command

## AVG

Give the average.

```sql
SELECT AVG(grade)
FROM grades;
```

## COUNT

```sql
SELECT COUNT(*) FROM student;

SELECT COUNT(DISTINCT(car_model)) from car;
```

used with distinct, it will not count duplicate.

## LOWER/UPPER

String function that convert character to lower/upper case

```sql
SELECT UPPER(name) FROM student;
```

## MIN/MAX

Return the min/max value from a column.

```sql
SELECT MAX(grade) FROM grade;
```
---

# Other Commands

Here are some other useful commands:

* .quit: exits the SQLite3 prompt
* .schema: shows the schema of all tables
* .mode column: changes the display mode to columnar
* .mode table: changes the display mode to tabular
* .timer on: displays the time it takes to execute a query


<br><br>

---

# Data Types

Here are the most common data types used in SQLite3:

* INTEGER: a whole number
* REAL: a decimal number
* TEXT: a string of characters
* BLOB: binary data

<br><br>

---

# Constraints

Here are some common constraints that can be applied to columns:

* NOT NULL: disallows null values
* UNIQUE: ensures that all values in the column are unique
* PRIMARY KEY: uniquely identifies each row in the table
* FOREIGN KEY: creates a link between two tables

<br><br>

---

# SQL Injection Attack

SQL injection attacks can be prevented by using parameterized queries or prepared statements. Avoid using user input directly in SQL queries, as it can allow malicious code to be executed.


# Race condition

If a lot of operation  are executed at the same time they can interfere each others.

Ex: everybody like smth on insta at the same time, instead of going from 100 likes to 103, 101 can be registered 2 times and we get 102

Solution: 

- BEGIN TRANSACTION
- COMMIT
- ROLLBACK
- (LOCKING) not used a lot
