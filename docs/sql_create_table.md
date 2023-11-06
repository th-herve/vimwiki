# Sql create table

To create a new table, use the following syntax:

```sql
CREATE TABLE <table name> (
  id INTEGER,
  foreign_id INTEGER
  <column name> <data type>,
  PRIMARY KEY (id),
  FOREIGN KEY (foreign_id) REFERENCES foreign_table(id);
);
```
Typing primary key (id), allow to create and increment automatically the id each new entry

For example, to create a table called "students" with two columns "name" and "age":

```sql
CREATE TABLE students (
  id INTEGER,
  name TEXT,
  age INTEGER,
  house_id INTEGER,
  PRIMARY KEY (id),
  FOREIGN KEY (house_id) REFERENCES houses (id);
);
```

> `Note`: primary key can only be specified inline: `id INTEGER PRIMARY KEY`
 
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

