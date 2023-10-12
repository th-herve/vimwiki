# Sql create table

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

## Create table from another one

Use `CREATE TABLE AS SELECT` or `SELECT INTO`

```sql
CREATE TABLE slitherin
AS SELECT *
FROM student
WHERE house = slitherin;

SELECT *
INTO slitherin
FROM student
WHERE house = slitherin;
```

